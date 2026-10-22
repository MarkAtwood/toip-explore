# Kernel enforcement of ToIP-governed ISM labels on Linux

**Status:** design sketch, revision 1. Nothing is implemented and no code
exists. This is a companion to [ism-oracle.md](ism-oracle.md) and reuses
its credentials, oracle, attestations and release agent unchanged. Kernel
interfaces marked *verify* are from memory. Check them against the target
kernel (this workstation runs 6.17) before relying on them.

## The idea in one paragraph

Files and directories carry ISM markings in extended attributes. A small
set of BPF LSM programs enforces access in the kernel, but they decide
nothing. They look up a verdict cache that a userspace **release agent**
fills, and the agent fills it only after the full ToIP flow:

- an oracle evaluation of the marking;
- the reader's clearance ACDCs in good TEL state;
- an access-decision attestation for *this* session and *this* file.

Anything not in the cache is denied. The kernel never parses ISM, verifies
a signature or talks to the network. It is a fast, fail-closed cache of
attestations.

The joke writes itself: the NSA already put mandatory access control into
Linux as SELinux. This replaces its central policy file with signed
credentials and ends up exactly as centralised.

## Rejected alternatives

| Option | Why not |
|---|---|
| **SELinux MLS / MCS** | Forces ISM into a dominance lattice it does not have; "releasable to" is not dominance. Caps compartments at 1024 categories. Makes the ISM-to-label mapping code, which breaks the oracle's main rule. |
| **AppArmor** | Path-based. Labels have to travel with the inode, not the path. |
| **fanotify permission events** (as in fapolicyd) | Can block on open and ask userspace, which is attractive. But it sees no per-read or per-write checks, so revocation doesn't reach open files. It has no per-task taint tracking for write-down, and puts a userspace round trip on every open. Kept as a possible cache-miss path only (see open questions). |
| **A new in-tree LSM** | A custom kernel build and permanent maintenance, for nothing BPF LSM cannot do. |
| **Landlock** | Built for a process to restrict itself, so it is unprivileged and voluntary. This needs mandatory control. |

BPF LSM stacks with whatever LSMs are already enabled. SELinux or AppArmor
can keep doing their own jobs alongside it.

## Governing constraints

1. **The kernel holds no policy.** BPF programs compare opaque identifiers
   (SAIDs, digests, session indexes) against maps. Every ISM or ToIP
   judgement happens in userspace, through the oracle design.
2. **Fail closed.** A missing map entry, an expired entry, an unknown label
   or an unlabelled file in a labelled tree all mean deny.
3. **Labelled content is immutable.** Each labelled file is an fs-verity
   file, so the kernel holds its content digest and refuses writes. An
   edit produces a new file that must be labelled anew. This removes the
   whole class of "content changed after it was labelled" problems.
4. **Access is requested, not ambient.** A miss is not resolved inside the
   syscall. The kernel denies, and the user asks through a tool that runs
   the IPEX `apply` flow. That mirrors the design's release exchange, and
   it is the "schedule your read-in" joke in kernel form.
5. **Sessions, not users.** Clearance binds to a login session that a
   reader AID has authenticated, not to a Unix UID. Sharing a UID across
   people doesn't share clearance.
6. **No ISM limits beyond ISM's own.** There is no category cap, no
   lattice assumption and no label translation table in the kernel. The
   only limits are Linux's, listed below.

## Components

| Component | Where | Role |
|---|---|---|
| BPF LSM programs | kernel | Enforce map verdicts on LSM hooks, track per-task taint, emit miss events to a ring buffer |
| Verdict maps | kernel | `(session, part SAID) → {verdict, fs-verity digest, expiresAt}`, plus write-allow entries |
| Release agent (`toipd`) | userspace, root | The PEP from ism-oracle.md. Runs IPEX, checks TELs, gets oracle evaluations, fills and evicts maps, and guards the BPF programs |
| Oracle | userspace, same enclave | Unchanged. Runs ISM via the package and release-policy credentials |
| PAM module | userspace | KERI-signed challenge at login; binds the session's cgroup to the reader's AID |
| `toip-apply` | userspace tool | Requests access to a path; drives IPEX `apply` |
| `toip-label` | userspace tool | Labeller's tool. Seals a file with fs-verity, writes the xattrs, and issues the part ACDC |
| `toip-ls` | userspace tool | Shows each file's banner by running the oracle's banner-rendering `transform` entry point. This is the ISM-native equivalent of SELinux's `mcstrans` |

## On-disk representation

**Files.** Each labelled file carries these extended attributes, in the
`security.bpf.*` namespace (*verify*: added for BPF LSM use in recent
kernels; otherwise `security.toip.*`, set only by `toipd`):

| xattr | Value |
|---|---|
| `security.bpf.toip.part` | The part ACDC's SAID |
| `security.bpf.toip.label` | The file's ISM marking as an exclusive-C14N XML fragment |
| `security.bpf.toip.acdc` | The compact part ACDC (optional; a label store can hold it instead) |

The part ACDC commits to the fs-verity digest of the content and to the
label. File content stays as the file's bytes; it is not inside the ACDC.

**Directories.** A directory is the labelled object, and its files and
subdirectories are its parts. It carries:

- `security.bpf.toip.object`: the SAID of the directory's labelled-object
  ACDC, whose skeleton covers every child.
- `security.bpf.toip.label`: the directory's banner marking.

Adding, removing or renaming a child changes the skeleton. That requires
a new directory ACDC, and the oracle's `ROLLUP` and full rule set must
pass first.

**Unlabelled files inside a labelled tree** are denied to labelled
sessions (constraint 2). That stops someone planting an unlabelled file in
a classified directory to collect copies.

## Flows

### Login

1. PAM challenges the user's KERI controller. The user signs, the module
   verifies against the AID's KEL, and the session is created in its own
   cgroup.
2. `toipd` records `cgroup id → session index → reader AID` in a map.
3. `toipd` pre-loads clearance and access ACDC status for that AID from the
   TELs (registries and witnesses are inside the enclave). Nothing is
   granted yet.

### Opening a labelled file to read

1. **`file_open`.** The program reads `security.bpf.toip.part` (*verify*:
   `bpf_get_file_xattr` kfunc) and gets the session index from
   `bpf_get_current_cgroup_id`. It looks up `(session, part)`.
   - If an entry exists and has not expired, the program compares the
     file's fs-verity digest (*verify*: `bpf_get_fsverity_digest` kfunc)
     with the cached one. If they match, the open is allowed.
   - Otherwise it returns `-EACCES` and pushes `(session, part, path
     hint)` to the ring buffer.
2. **`toip-apply <path>`.** This runs IPEX `apply` with `toipd`. `toipd`
   checks the release policy's evaluation of the file's labelled object
   and the reader's clearances, and issues an access-decision attestation.
   Only then does it write the map entry, with `expiresAt` copied from the
   attestation. The user retries.
3. On success the program records the part's label in the task's taint set
   (see below).

### Every read, write and mmap

- **`file_permission`** re-checks the map entry on each `read`/`write`.
  Revoking it therefore takes effect on the next syscall, even on file
  descriptors that are already open.
- **`mmap_file`** denies shared mappings of labelled files. Pages that are
  already mapped can't be revoked, so a mapping would make revocation
  unenforceable. Private read-only mappings are allowed only when the
  release policy marks the deployment as accepting that gap.

### Revocation

`toipd` watches the TELs. When a clearance or access ACDC is revoked, it
deletes every map entry that depended on it. Each access-decision
attestation lists its clearance edges, so the dependency set is known. It
also kills or freezes (cgroup freezer) any task in that session that is
tainted by the revoked access.

### Creating or writing labelled content (no write-down)

Every task carries a **taint set** in BPF task-local storage: the labels of
everything it has read. `task_alloc` copies the set to children, and
`bprm_check_security` keeps it across `exec`.

A write to a target is allowed only if the target's marking dominates the
task's taint. The kernel can't evaluate dominance, and the design refuses
to encode an ISM lattice. So dominance is decided by ISM's own rules:

1. `toipd` builds a synthetic skeleton. Its banner is the target's marking,
   and its portions are the task's taint set.
2. The oracle runs the full rule set over it. ODNI's banner-versus-portion
   rules (ISM-ID-00056/58/59 and the dissemination roll-up rules) pass
   only if the banner covers every portion.
3. If the result is `noViolationsFound`, `toipd` caches
   `(taint-set SAID, target-label SAID) → allow`.

Because labelled files are immutable (constraint 3), "writing" means
creating a new file. The create is allowed in a directory only if the
directory's label passes the same check. The new file stays unreadable to
everyone until a labeller seals and labels it with `toip-label`. A tainted
process cannot publish anything on its own authority.

### Moving data any other way

A tainted task is boxed. The hooks below deny it from:

| Channel | Hook (*verify* names on target kernel) |
|---|---|
| Network | `socket_connect`, `socket_sendmsg` (deny all except the enclave's `toipd` socket) |
| Unix sockets to a less-tainted peer | `unix_stream_connect`, `unix_may_send` (allowed only if the peer's taint set is the same) |
| Writing unlabelled files | `file_permission` (write), `inode_create` outside labelled trees |
| Changing labels | `inode_setxattr`, `inode_removexattr` on `security.bpf.toip.*` (only `toipd` may) |
| Hard links and renames out of a labelled tree | `inode_link`, `inode_rename` |
| Tracing another task | `ptrace_access_check` across sessions |

Pipes between tasks in the same session inherit nothing explicitly, but
both ends are in the same session and only one taint set travels, which is
conservative. Shared memory (`shm_*`, `memfd`) follows the unix-socket
rule.

### Self-protection

The `bpf` hook denies loading, detaching or replacing BPF programs and
maps to anything except `toipd`. The `security.bpf.toip.*` hooks above
protect the labels. Lockdown (`lockdown=confidentiality`) closes
`/dev/mem`, `kexec` and similar ways to tamper with the running kernel.

## Linux limits, and how each is handled

| Limit | Handling |
|---|---|
| xattr value at most 64 KiB (`XATTR_SIZE_MAX`). ext4 fits roughly one block per inode unless `ea_inode` is enabled. | Store the SAID and the marking fragment, which is small, and keep large ACDCs in a label store. Require XFS, or ext4 with `ea_inode`. |
| BPF programs cannot block waiting on userspace. | Deny-and-apply (constraint 4). Not a workaround: it matches the release protocol. |
| Per-task storage and map memory are bounded. | Taint sets are capped. A task that reaches the cap is frozen, not allowed. Its taint is stored as one SAID of the set, with the members held by `toipd`. |
| fs-verity files are read-only and need filesystem support (ext4, f2fs, btrfs). | Constraint 3 makes read-only a feature. Other filesystems cannot hold labelled content. |
| Mapped pages cannot be revoked. | Deny shared mmap of labelled files; private mappings follow release policy. |
| Root can unload, reboot or boot another kernel. | Lockdown plus self-protection covers the running system. Offline attacks need measured boot (IMA plus TPM). `toipd` could refuse to serve a host whose TPM quote doesn't match. Root is otherwise trusted, as in SELinux. |
| NFS and network filesystems carry `security.*` xattrs inconsistently. NFSv4.2 labels (RFC 7204) carry one security label, not arbitrary xattrs. | Labelled content lives on local fs-verity filesystems only. |
| Containers share the kernel. | Sessions are cgroups, so a container is just another session tree. User namespaces can't grant `security.*` writes. |
| A display server, clipboard or printer moves data through processes the LSM doesn't model as labelled. | **Out of scope.** Run labelled sessions without a shared display, or treat the display server as a tainted task in the same session. |

## Threats specific to this layer

- **Time-of-check to time-of-use between the map and the TEL.** Map
  entries expire with the attestation (minutes). Revocation evicts eagerly,
  and `file_permission` re-checks on every syscall.
- **Content swapped under a label.** fs-verity digests are checked at
  open against the digest committed in the part ACDC.
- **Label swapped on disk.** The xattr hooks restrict writers to `toipd`.
  Offline edits break the part SAID, which `toipd` re-verifies before
  caching.
- **Leaking through the denial.** `-EACCES` is the same whether a file is
  classified, missing a label or simply not yet applied for. The ring
  buffer event goes to `toipd`, which notifies the owner, not the user.
- **`toip-ls` as an oracle for the curious.** Banners are rendered only
  for parts the session has been granted. Otherwise it shows
  `[not granted]` and the SAID, which is the "you don't get to read this
  part" behaviour.

## Open questions

1. **Hook and kfunc availability on 6.17.** Confirm that `bpf_get_file_xattr`
   can read `security.bpf.*`, that `bpf_get_fsverity_digest` is callable from
   `file_open`, and which of these hooks are sleepable.
2. **A blocking miss path.** Should a cache miss block on a fanotify
   permission event instead of deny-and-apply? It would be friendlier for
   legacy programs, but it puts a userspace round trip in the syscall.
3. **Taint granularity.** Per task, or per thread? Threads share memory, so
   per task (`tgid`) is the honest unit. That is coarse for servers.
4. **Declassification.** Lowering a label is a new file plus a labeller
   decision. Is a separate "declassifier" authority credential required,
   distinct from the labeller's?
5. **Performance.** One map lookup per `read`/`write` on labelled files,
   and an oracle round trip on every new combination of taint set and
   target label. Unmeasured.
