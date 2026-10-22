# DTG VSC Predicate Registry

The registry of predicates for the **Verifiable Statement Credential (VSC)** defined in the [DTG Credentials Core Specification](https://github.com/trustoverip/dtgwg-cred-spec), maintained by the Decentralized Trust Graph Working Group (DTGWG) of the [Trust Over IP Foundation](https://trustoverip.org).

> **Status.** The definition format, build tooling and the first four predicates (`endorses`, `witnessed`, `vetted`, `presented`, all `draft`) are in, and the registry is served at `registry.trustoverip.org`. `endorses/1` and `witnessed/1` are the normative definitions of the specification's two core profiles, the VEC and the VWC; the specification refers to them. The handoff of that deployment to an account the Trust Over IP Foundation owns follows (GOVERNANCE §4.3); until it completes, no predicate is promoted past `draft`.

- **Published registry:** <https://registry.trustoverip.org/dtg>, with the predicates at <https://registry.trustoverip.org/dtg/vsc>
- **Rules:** [`GOVERNANCE.md`](GOVERNANCE.md), admission, versioning, statuses, review
- **Design and deployment plan:** [`PLAN.md`](PLAN.md)
- **Definition format:** `meta/predicate.schema.json` (arrives with the tooling)
- **Individual predicates:** `predicates/<name>/<n>/`

## What a predicate is

A VSC carries one signed statement by one DTG node about another: a subject, a **predicate**, and an object. The predicate is an absolute IRI drawn from a governed vocabulary, and it is the credential's single channel of meaning. This registry publishes the vocabulary the DTGWG curates under a namespace the Trust Over IP Foundation controls. Every predicate here has a definition that states, as the specification's *Predicate Profiles* section requires, what the predicate means, what kind of object it takes, who may issue it, and what a successful verification establishes and does not.

The registry is a shared default set, not a gate. A community can define predicates under its own namespace in the same format and verifiers can accept them without admission here. See [`GOVERNANCE.md` §1](GOVERNANCE.md#1-what-the-registry-is-and-is-not).

## The identifiers, exactly

A predicate IRI is compared byte-for-byte, so its exact form matters. It is:

```
https://registry.trustoverip.org/dtg/vsc/<name>/<n>
```

for example

```
https://registry.trustoverip.org/dtg/vsc/endorses/1
https://registry.trustoverip.org/dtg/vsc/witnessed/1
```

`https`, no `www.`, no trailing slash, no fragment. `<n>` is a per-predicate integer version; each `<name>/<n>` is its own immutable term, and there is no compatibility between versions (see [`GOVERNANCE.md` §3](GOVERNANCE.md#3-versioning)). The bare `.../vsc/<name>` is a documentation page, never a predicate.

The credential `@context` the specification requires is published beside the vocabulary, versioned and frozen:

```
https://registry.trustoverip.org/dtg/context/v1
```

## How the registry is served

One URL serves both people and machines, by HTTP content negotiation:

| URL | `Accept: text/html` (or absent) | `Accept: application/ld+json` | `Accept: application/json` |
|---|---|---|---|
| `/` | the host's landing page: the registries served from `registry.trustoverip.org` | the same page | the same page |
| `/dtg` | this registry's home: its namespaces and where the rules live | the same page | the same page |
| `/dtg/vsc` | index of every predicate | `vocab.jsonld`, the whole graph | `accept-list.json`, for verifier import |
| `/dtg/vsc/<name>` | version history | 406 | 406 |
| `/dtg/vsc/<name>/<n>` | the profile page | the definition | 406 |
| `/dtg/context/v<k>` | what the context defines | the context | the context |

Every artifact is also reachable at an explicit file path (for example `/dtg/vsc/witnessed/1/predicate.jsonld`) for clients that do not negotiate. Verifiers resolve predicates at configuration time only, never at verification time, as the specification requires.

## Repository layout

```
predicates/<name>/<n>/      one folder per predicate version — the source of truth
  predicate.jsonld          the normative definition, validated against meta/
  profile.md                prose: rationale, notes, worked explanation
  *.schema.json             schemas for the object payload or additional members
  examples/*.json           complete credentials, validated by the build
contexts/vN.jsonld          frozen JSON-LD contexts, one per version
meta/                       the definition format and the accept-list schema
scripts/                    validate + generate dist/
site/                       templates, assets, and the Cloudflare worker
registry.config.json        the one file that names this instance (see below)
```

## Proposing a predicate

1. Read [`GOVERNANCE.md` §5](GOVERNANCE.md#5-admission-to-the-dtg-namespace), the admission criteria, and §2.3, the naming convention.
2. Fork, branch, and create `predicates/<name>/1/` with `predicate.jsonld`, `profile.md` and at least one example credential in `examples/`.
3. Validate locally (in Docker, no host install):
   ```sh
   docker compose run --rm validate
   ```
4. Commit with DCO sign-off (`git commit -s`) and open a pull request using the **New predicate** template. It carries the admission checklist.
5. Two editors review. A merged predicate starts at `draft`.

A new version of an existing predicate is proposed the same way, as `predicates/<name>/<n+1>/`, with `supersedes` set and the predecessor deprecated in the same pull request.

## Running your own registry

Nothing in the format or the tooling is specific to the DTG namespace. A community that wants to publish its own predicates in the same format, with the same validation, immutability checks, content negotiation and accept-list generation, can run this repository as its own registry:

1. Fork this repository.
2. Edit [`registry.config.json`](registry.config.json): set `namespace`, `contextBase`, `metaBase`, `siteUrl`, `siteName`, `hostName`, `indexName`, `maintainer`, `repository`, and `governedBy` (the URL of the governance framework that defines who may issue your predicates and how they are weighed).
3. Edit `name` in `wrangler.toml` to your Cloudflare Pages project name.
4. Add the `CLOUDFLARE_API_TOKEN` and `CLOUDFLARE_ACCOUNT_ID` secrets to your fork.
5. Push to `main`.

Those two files are the only places an instance-specific value is written; the CI validation fails if one appears anywhere else. The site takes the same shape at your host: `/` is a landing page naming the host (`hostName`) and listing the registries it serves, and the registry's own home is the parent path of `namespace` (`/dtg` here), with the predicates, contexts and definition format beneath it. A namespace directly under the host root makes `/` the registry's home and there is no separate landing page. What a fork does not inherit is admission to `/dtg/vsc/`, which is this registry's, and which a fork does not need: a verifier accepts your namespace by configuration exactly as it accepts this one.

## Contributing

Contributions are governed by the Trust Over IP Foundation's contribution process:

- Every commit **MUST** carry a DCO `Signed-off-by` trailer. Use `git commit -s`.
- By opening a pull request, contributors agree to the Open Web Foundation **Contributor License Agreement** in [`CONTRIBUTING.md`](CONTRIBUTING.md). That agreement grants the patent and copyright rights necessary to incorporate contributions into the published registry. The Linux Foundation's EasyCLA checks this on every pull request.
- Source code in this repository (`scripts/`, `site/`, `infra/`, build tooling) is contributed under the license in [`SOURCE_CODE.md`](SOURCE_CODE.md).

## Licensing

The published registry content (`predicates/`, `contexts/`, `meta/`, `GOVERNANCE.md`) is licensed under the Open Web Foundation **Final Specification Agreement** in [`LICENSE.md`](LICENSE.md), which grants implementers the patent and copyright rights needed to build conforming products against the published predicates. Source code is published under [`SOURCE_CODE.md`](SOURCE_CODE.md) (Apache-2.0).

| File | Direction | What it covers |
|---|---|---|
| `CONTRIBUTING.md` | *Contributor → Working Group* | Rights you grant when you contribute to the registry. |
| `LICENSE.md` | *Working Group → Implementer* | Rights granted to anyone implementing a published predicate. |
| `SOURCE_CODE.md` | Both directions, for code | License covering source code in this repository. |

This is the same arrangement the [Trust Tasks registry](https://github.com/trustoverip/dtgwg-trust-tasks-tf) uses.

## Getting involved

Discussion, issues and proposals live in this repository's [issue tracker](https://github.com/trustoverip/dtgwg-vsc-registry/issues). Design discussion that predates the repository is in the credential specification's issues [#48](https://github.com/trustoverip/dtgwg-cred-spec/issues/48) and [#52](https://github.com/trustoverip/dtgwg-cred-spec/issues/52). Join the community at <https://trustoverip.org/get-involved/membership/>.

# Governance of the DTG VSC Predicate Registry

This document states how a predicate enters this registry, how it is identified, versioned and promoted, and who reviews what. It applies to the namespace `https://registry.trustoverip.org/dtg/vsc/` and to the frozen contexts and definition format published beside it. The mechanism these rules serve, the Verifiable Statement Credential (VSC), is defined in the [DTG Credentials Core Specification](https://github.com/trustoverip/dtgwg-cred-spec); its *Predicate Handling*, *What Verification Establishes* and *Predicate Profiles* sections are normative for every predicate here, and this document does not restate them.

The design decisions behind these rules, with their sources in the specification's issue threads, are recorded in [PLAN.md](PLAN.md).

## 1. What the registry is, and is not

The registry curates a **shared default set** of predicates under a namespace the Trust Over IP Foundation controls. It is **not a gate**. A predicate is an absolute IRI that a verifier accepts by configuration, resolved at configuration time and never at verification time. A community that publishes a predicate under a namespace it controls, in the same definition format, can issue under it and verifiers can accept it without waiting on, or ever seeking, admission here. Admission is what a community seeks when it wants convergence, one identifier shared across communities, not what it needs in order to use the specification. The registry decides what enters the DTG namespace; it does not decide who may make a statement.

## 2. Identifiers

### 2.1 Form

A predicate IRI has exactly this form, in these bytes:

```
https://registry.trustoverip.org/dtg/vsc/<name>/<n>
```

- The scheme is `https`. The host is `registry.trustoverip.org`, never `www.`. There is no trailing slash, no query and no fragment.
- `<name>` is lowercase ASCII letters and digits, hyphen-separated, beginning with a letter: `^[a-z][a-z0-9]*(-[a-z0-9]+)*$`.
- `<n>` is a positive integer without leading zeros: `^[1-9][0-9]*$`.
- The IRI is in Unicode Normalization Form C. Since the grammar admits only ASCII, this is satisfied by construction.

Comparison is byte-exact on the IRI as written, as *Predicate Handling* requires. The registry never publishes two spellings of one term.

### 2.2 The bare name is not a term

`https://registry.trustoverip.org/dtg/vsc/<name>` (no version) serves the human-readable version history of `<name>` and nothing else. It **MUST NOT** be used as a predicate identifier in any credential. A request for it with a machine media type receives `406 Not Acceptable`.

### 2.3 Naming convention

A predicate name is an identifier, not a word; its spelling carries no normative meaning, and the language-tagged `label` values carry the human names. The convention below exists so that proposers have a rule and the registry reads consistently.

Names are English verb forms, and the form marks the statement's **aspect**, not its time:

- **third-person singular present** for a relation that holds for as long as the credential is valid: `endorses`;
- **simple past** for a completed observation or act, made once in an identifiable exchange: `witnessed`, `presented`, `vetted`.

The circumstances of a statement (when, where, by what method, in which exchange) are never encoded in the name. They belong in `taskContext`, `validFrom`, the profile's additional members, or a verifiable data structure the statement references by digest, as the profile defines.

The infinitive is not used. Trust Task slugs are imperative forms (`grant`, `revoke`, `witness/session`); keeping predicates in a different grammatical form preserves the statement-versus-task distinction at a glance.

### 2.4 Two version axes

Predicate versions are bare integers (`/witnessed/1`). Context versions carry a `v` (`/dtg/context/v1`). This is deliberate: the two are independent axes, and `vN` is the form the already-deployed credential context uses and the form reserved in the design discussion for "the registry-wide `context/vN.jsonld` axis" ([cred-spec #52, comment](https://github.com/trustoverip/dtgwg-cred-spec/issues/52#issuecomment-5684061231)).

### 2.5 Reserved paths

`/dtg/context/`, `/dtg/credentials` and `/dtg/meta/` are not vocabularies of predicates and no predicate name is minted under them. `/dtg/context/vN` is a credential context (§3.1) and `/dtg/credentials#` is the unversioned namespace of the type and property IRIs those contexts define. A new vocabulary under `/dtg/` (for example VDC `scope` terms or VAC `actions`) gets its own sibling of `vsc/` and its own definition format.

## 3. Versioning

A predicate's IRI takes the form `.../vsc/<name>/<n>`, where `<n>` is a positive integer, private to that predicate and independent of every other predicate's counter and of the context version.

Each `<name>/<n>` is **immutable and opaque once published**. "Versioning" here names a convention for successive deprecate-and-add terms whose successor's name is systematically derived from the predecessor's; it is **not a compatibility promise**. There is no forward- or backward-compatible acceptance between versions of the same predicate. A verifier configured for `<name>/<n>` **MUST** fail closed on `<name>/<n+1>` until explicitly reconfigured.

A published predicate **MUST NOT** change meaning. Meaning changes are never permitted: the change is a new version, and the predecessor is marked `deprecated` with `supersededBy` pointing at the successor in the same pull request. Minting a new version follows the same review path as a new term (§6).

Nothing is ever deleted. A deprecated term is published forever, marked, with a pointer to its replacement if one exists.

### 3.1 Contexts

A credential `@context` published under `/dtg/context/vN` is the wire-level shape of every DTG credential, not only the VSC, and the [DTG Credentials Core Specification](https://github.com/trustoverip/dtgwg-cred-spec) is its authority. The registry hosts and freezes it; the specification's editors decide what it contains and when a new version is minted. A new version is minted when the specification adds, renames or retypes a term that credentials carry; nothing else justifies one. That includes the additional members of a predicate profile (`witnessContext`, for example): profile members are defined in the core context rather than in a context of their own, so adding one is a new core version. The type and property IRIs a context defines live under `https://registry.trustoverip.org/dtg/credentials#`, which carries no version segment: a term keeps its IRI across context versions, as a predicate does.

A published context is **byte-frozen**. It is never edited, not even editorially: additions and renames go in `vN+1`, and every version ever published stays served at its IRI. A context never redefines a term the W3C Verifiable Credentials context defines and protects (`digestMultibase`, for example), because JSON-LD processors reject the redefinition.

Changes under `contexts/` follow the specification's editorial process, not the predicate rules of §5. A pull request that adds a context version is opened by, or approved by, the specification's editors, who are the `contexts/` owners in [CODEOWNERS](.github/CODEOWNERS), and it links the specification pull request that makes the matching change to *Base Structure*. The two land together.

## 4. Statuses

Every predicate version carries one status. The lifecycle is [Trust Tasks SPEC §5.3](https://trusttasks.org/SPEC#53-maturity-levels) transposed to predicates.

| Status | Meaning | Stability |
|---|---|---|
| `draft` | Merged, not yet demonstrated in independent use. Editorial changes may be made in place. | Not stable. |
| `candidate` | Definition frozen except editorial clarification. Requires **two independent, interoperable consumers** of the predicate before entering this status. | Stable. |
| `standard` | A `candidate` that has completed a **continuous 90-day window with no meaning change**. | Stable. |
| `deprecated` | Kept forever, marked, pointing at any replacement. Producers **SHOULD NOT** issue new statements under it. | Frozen. |

Two deliberate differences from Trust Tasks: the terminal status is called `deprecated` rather than `retired`, because that is the word the credential specification's *Predicate Handling* uses, and "no breaking changes" becomes "no meaning change", because a predicate has no non-breaking change to make.

### 4.1 Permitted transitions

- `draft` → `candidate`, once the entry criteria are met.
- `candidate` → `standard`, once the 90-day window has elapsed.
- any status → `deprecated`.

`deprecated` is terminal. Reviving a meaning is a new `<name>/<n+1>` starting at `draft`.

### 4.2 In-place changes

While a version is `draft`, editorial changes (label additions, rewording that does not alter meaning, corrected examples) are made in place. From `candidate` onward, **no change** to a normative member is permitted, including relabeling: the only members that may change are `status`, `since`, `deprecatedOn` and `supersededBy`, and the prose in `profile.md`. The build enforces this by diffing every non-`draft` version against `main`.

### 4.3 Promotion gate on hosting

No predicate is promoted past `draft` until the deployment serving `registry.trustoverip.org` is in a Cloudflare account owned by the Trust Over IP Foundation and the custom domain resolves there. The IRIs are anchored by the DNS record ToIP controls, so a term's identity never depends on whose account is behind it; the gate is about availability and continuity, because a `candidate` term is one other implementations have started to configure against.

Handoff completed: *not yet*.

## 5. Admission to the DTG namespace

A proposed predicate is accepted when it:

1. is complete against `meta/predicate.schema.json`, including the establishes / does-not-establish block;
2. is on the **attests** side of the statement/establishment test: it is not a predicate whose PASS a verifier would act on as representation, authority, membership, admission, governed status or task completion;
3. is **unilateral**: its issuer alone signs it and it is complete without any counterparty's participation;
4. is not meaningful only inside one exchange (that is a trust task artifact, not a statement);
5. has **no existing term with the same meaning**: one identifier per concept;
6. has an NFC IRI in the form of §2.1 and at least an English label;
7. is either needed by a DTG specification, or in use, or credibly about to be, by more than one community.

**Convergence from a community namespace.** Criterion 5 does not block admitting a DTG-namespaced successor to a community term when the community asks for convergence. In that case the new term's definition names the community IRI in `supersedes` and links, in `convergenceRecord`, the commit or pull request in the community's own repository that marks its term superseded by this one. The definition format rejects the first without the second, and the reviewers confirm the link points at a merged change that says what it should.

## 6. Review

Changes are made by pull request against `main`. Every commit carries a DCO `Signed-off-by` trailer, and every contributor has accepted the contribution terms in [CONTRIBUTING.md](CONTRIBUTING.md), which EasyCLA enforces.

| Change | Approvals |
|---|---|
| New term, new version of a term, or status promotion | Two editors from the `predicates/` owners in [CODEOWNERS](.github/CODEOWNERS) |
| Deprecation | Two editors |
| Editorial change to a `draft` version, or to `profile.md` of any version, that the immutability check confirms touches no normative member | One editor |
| New context version | Two of the `contexts/` owners in CODEOWNERS, with the matching specification pull request linked (§3.1) |
| Any change to a published context | Refused; the change is a new version (§3.1) |
| Tooling, site, workflows | One owner of the affected path |

Meaning changes are not reviewed; they are refused. Deprecate and add.

## 7. Equivalence

The registry **MAY** record, in a version's `profile.md` and as an informative `seeAlso` member, that a community term has the same meaning as a DTG term. This is information for the people configuring verifiers. Verifiers never follow it: *Predicate Handling* forbids accepting a predicate on the strength of any published equivalence.

## 8. What to pin

Every push to `main` publishes the current state. The registry is not tagged and has no release versions of its own: its unit of immutability is each `<name>/<n>` and each `context/vN` (§3), and a credential names those IRIs, never a registry version. `accept-list.json` carries the `commit` it was built from, and every build publishes `release.json` with a SHA-256 digest of each file it serves, plus a `.sha256` sidecar beside the machine-readable artifacts. An implementation that bundles an immutable copy, or a verifier that pins what it imported, pins that commit or the digest of the `accept-list.json` it fetched. Which registry IRIs a specification depends on is recorded in that specification's own release.

## 9. Changing this document

This document is registry content: two editor approvals, as in §6. Changes to §2.1 (the IRI form) or §3 (versioning) after the first non-`draft` term exists are breaking for every issued credential and are not expected to be made.

# Predicate `endorses/1`

A statement under this predicate is a **verifiable endorsement credential (VEC)**, one of the two core profiles the [DTG Credentials Core Specification](https://github.com/trustoverip/dtgwg-cred-spec) names. This entry is the profile's normative definition; the specification's *VEC* section states what the profile is and refers here for its members. Verifiers configure against this entry, as the specification's *Predicate Handling* requires.

## What the object carries

The object is a `value` whose structure is defined by the governing community's endorsement vocabulary, not by this profile. The specification's example endorses a skill:

```json
"object": { "value": { "type": "SkillEndorsement", "name": "Software Development", "competencyLevel": "expert" } }
```

A verifier applies whatever schema its governing framework publishes for that vocabulary. This registry validates only that the object is a `value`.

## Why the bound is narrow

An endorsement is evidence. What "verifiable" means here is that the signature is the issuer's, not that the endorsement is true, and not that the issuer was in a position to give it. Who may endorse what, and how much an endorsement counts, is the governing community's decision, applied through configuration and governance rather than read off the credential.

## Notes for implementers

- `taskContext` is optional. An endorsement is meaningful standing alone; a community may still require it for endorsements made in a ceremony.
- The profile places no constraint on the issuer's correlation scope.
- The specification writes the predicate as `dtg:endorses`, documentation shorthand for the IRI on this page; on the wire a predicate is always the absolute IRI.

```json
{
  "@context": "https://registry.trustoverip.org/dtg/meta/v1/predicate-context.jsonld",
  "id": "https://registry.trustoverip.org/dtg/vsc/endorses/1",
  "type": "Predicate",
  "name": "endorses",
  "version": 1,
  "status": "draft",
  "label": {
    "en": "endorses"
  },
  "definition": {
    "en": "The issuer asserts something favorable about the subject: a skill, a standing, a reputation. The vocabulary of what may be endorsed is defined by the governing community."
  },
  "classification": "evidence",
  "weighedBy": "The governing VTC or VTN, whose endorsement vocabulary defines what may be endorsed and what weight an endorsement carries.",
  "objectKind": ["value"],
  "objectSchema": null,
  "objectSchemaDelegated": true,
  "subjectObjectRelationship": null,
  "additionalMembers": {},
  "taskContextRequired": false,
  "minimumIssuerScope": null,
  "issuer": "A party to a DTG edge with the subject, or a VTA acting under community policy.",
  "establishes": "That the issuer endorsed the subject with the given payload.",
  "doesNotEstablish": [
    "that the endorsement is accurate; the verifiability of an endorsement applies to the issuer's signature, not to the truth of the assertion",
    "that the issuer is qualified to give it, which is for the governing framework to say",
    "that the subject holds any membership, authority or status"
  ],
  "definedIn": null,
  "governedBy": null,
  "supersedes": null,
  "supersededBy": null
}

```

# Predicate `presented/1`

A statement under this predicate records that a party showed a credential it holds. The witness observed the *holder* present the credential the object names; the credential's issuer may never have been in the room. A door service attesting that a member presented their membership credential at an event is the typical case.

This is the presentation, or custody, statement asked for in review of the specification's statement credential, and it is the counterpart the `witnessed/1` profile points to under *What this predicate is not*.

## Why its own predicate

`witnessed/1` binds its subject to the **issuer** of the referenced credential, so each statement names one direction of an edge. A presentation is observed from the other side: the observed party is the referenced credential's **subject**. Stretching `witnessed/1` to cover both would make one IRI carry two subject–object rules, and a verifier could no longer check which one a statement meant.

## What the digest binds

`object.digestMultibase` names the presented credential, computed as the specification's *Digest Encoding* section defines, over the credential excluding its top-level `proof`. A verifier holding that credential checks that its `credentialSubject.id` is this statement's `credentialSubject.id`. Without the credential to hand, the digest is an opaque hash, not an identified credential.

## Status

No implementation issues this statement yet. It enters as `draft` so that the identifier exists when one does, and it stays `draft` until something uses it. Promotion to `candidate` needs two independent, interoperable consumers (GOVERNANCE §4).

## Notes for implementers

- `taskContext` and, with it, `taskDigestMultibase` are required: a presentation is meaningful only relative to the exchange it happened in.
- The issuer's correlation scope is `directed` at minimum, for the same reason as `witnessed/1`: the witness must be recognizable to the community whose policy it applies.
- A verifier cannot tell from this statement whether the holder proved control of the presented credential's subject identifier, so the statement never establishes it. A verifier that needs it checks it in its own exchange.
- The example's identifiers and digests are illustrative.

```json
{
  "@context": "https://registry.trustoverip.org/dtg/meta/v1/predicate-context.jsonld",
  "id": "https://registry.trustoverip.org/dtg/vsc/presented/1",
  "type": "Predicate",
  "name": "presented",
  "version": 1,
  "status": "draft",
  "label": {
    "en": "presented"
  },
  "definition": {
    "en": "The issuer attests that it observed the subject present the credential the object names, under the conditions of a specific trust task exchange. The subject is the holder; the credential's issuer need not have been present."
  },
  "classification": "evidence",
  "weighedBy": "The community whose policy the attestation is issued under.",
  "objectKind": ["digestMultibase"],
  "subjectObjectRelationship": "credentialSubject.id MUST be the credentialSubject.id of the credential object.digestMultibase names, and a verifier holding that credential MUST check that it is.",
  "additionalMembers": {},
  "taskContextRequired": true,
  "minimumIssuerScope": "directed",
  "issuer": "A member, or a VTA acting according to VTC policy.",
  "establishes": "That the issuer attests that, in the exchange identified by taskContext, the subject presented the credential whose claims digest to object.digestMultibase.",
  "doesNotEstablish": [
    "that the presented credential is currently valid or unrevoked; the digest excludes its proof and its status, so the attestation is about those claims at the moment of presentation",
    "that the presented credential's claims are true",
    "that the subject controls the presented credential's subject identifier",
    "that the exchange reached its terminal state, which requires the outcome evidence of the specification's Outcome Interpretability rules",
    "that any consequential action is authorized"
  ],
  "definedIn": null,
  "governedBy": null,
  "supersedes": null,
  "supersededBy": null
}

```

# Predicate `vetted/1`

A statement under this predicate records one peer identity check. An existing member of a community, the *vetter*, checks in person or on video that an *applicant* is who they claim to be and controls the identifier they will join with, and records that check as a statement. The community collects several such statements and decides admission on them.

The community itself may also be the issuer. When its own operators check a member's identity, at a desk or in person, the community records that check as a statement under its own DID. It does not mint a separate credential type for it. Every identity check in the graph then has one shape, whoever made it.

A statement the community issues for itself carries none of the three vetter-only members: `identityCommitment`, `cardDigestMultibase` and `declaredRelationship`. That is a requirement, not an omission for convenience. The salt behind `identityCommitment` travels to vetters inside the card and never to the community. A community holding it could test candidate values against every vetter's commitment, which is exactly what the construction exists to prevent. The community links its own statement to its vetters' statements by the subject identifier, not by commitment.

The DTG Credentials Core Specification uses this profile as its informative worked example of a community-defined predicate, under an illustrative community namespace. This entry is the normative definition of the profile in the DTG namespace, so that communities running peer vetting can share one identifier for it. Where the two differ, this entry governs.

## Why its own predicate

A vetting statement is a record of a procedure: a named member carried out a check, by a stated method, against stated classes of document, on a stated date.

- `endorses/1` would carry the payload, but it would also say that the vetter *endorses* the applicant. That is not what the vetter did, and it is not what the community weighs.
- `witnessed/1` is about observing a credential being issued in an exchange. A vetting statement names no credential.

A vetting statement is also made before any edge exists. The vetter and the applicant may share no relationship, and the applicant is not yet a member. A statement annotates a node, so nothing has to be invented to explain what edge it presumes.

## What the object carries

The object is a `value` whose shape this profile fixes, in `vetting.schema.json`. The three vetter-only members are present together or absent together, and the schema enforces that with `dependentRequired`:

| Member | Meaning |
|---|---|
| `community` | DID of the one community the statement was made for. A statement does not count anywhere else. |
| `method` | `inPerson`, `video` or `priorAcquaintance`. |
| `documentClasses` | Classes of identity document relied on, for example `passport`. Empty or absent for `priorAcquaintance`. Never a document number, image or portrait. |
| `claimsVerified` | Claim *types* checked against the person, for example `name.legal`. Claim values never appear. |
| `livenessConfirmed` | Whether the vetter confirmed, during the session, that the person in front of them controlled `credentialSubject.id`. |
| `identityCommitment` | A salted commitment to the identity claims the applicant presented. Vetter-only: a vetter's statement always carries it, and a community-issued statement never does (see above). |
| `cardDigestMultibase` | Digest of the signed card the applicant presented, over the card exactly as the vetter received it. It lets a dispute identify the exact card relied on without the community ever receiving it. Vetter-only, on the same terms as `identityCommitment`. |
| `declaredRelationship` | `none`, `communityColleague`, `sameEmployer`, `family` or `otherPersonal`, so a community can limit how many statements from related vetters it counts. Vetter-only: the community is the party weighing the statements, so a statement it issues for itself does not carry this member. |
| `attestationTextDigest` | Optional. Digest of the governance text the vetter was shown before signing. |

Enumerated values are camelCase, the convention the VC Data Model 2.0 and Data Integrity use for their own values (`assertionMethod`, `revocation`). The specification's worked example is aligned to the same spelling.

## Notes for implementers

- `taskContext` is required: it names the vetting exchange in which the check happened. For a community's own check, that exchange is the request in which the community recorded it. The statement remains true afterwards, so it is a credential rather than a trust task artifact, but the exchange is what a dispute would examine.
- The issuer's correlation scope is `directed` at minimum. The vetter must be recognizable to the community weighing the statement, so a `pairwise` declaration could not describe it truthfully.
- Eligibility to vet is conferred by the community. A verifier checks it under community policy, never from this statement. A statement the community issued for itself needs no eligibility check: its issuer is the community it names.
- **This statement is evidence, not a status.** Personhood, like admission, is the community's decision, recorded on its membership credential (as the specification's *Personhood Credentials* section describes). A community may require one or more `vetted/1` statements, its own or its vetters', before deciding it. A verifier acts on the decision, not on the statement.
- Identity credentials from outside providers (a government eID, a commercial identity-verification provider) are not statements under this predicate. The specification treats them as any W3C credential meeting the community's identity-proofing rules.
- The three digest-valued members are unsalted digests, and cred-spec issue #38 (blinding for digest-valued binders) and #58 (a committed form of the task citation) may change how they are carried. This version stays `draft` until both are settled.
- The examples' identifiers and digests are illustrative. `video-vetting.json` is a vetter's statement; `community-desk-check.json` is the community recording its own check.

```json
{
  "@context": "https://registry.trustoverip.org/dtg/meta/v1/predicate-context.jsonld",
  "id": "https://registry.trustoverip.org/dtg/vsc/vetted/1",
  "type": "Predicate",
  "name": "vetted",
  "version": 1,
  "status": "draft",
  "label": {
    "en": "vetted"
  },
  "definition": {
    "en": "The issuer attests that it checked the subject's claimed identity in a vetting session, by the method and against the document classes the object states."
  },
  "classification": "evidence",
  "weighedBy": "The community named in object.value.community, when it decides admission or personhood. A statement is not a decision. A community may require several from distinct vetters, may record its own check as a statement it issues for itself, or both.",
  "objectKind": ["value"],
  "objectSchema": "https://registry.trustoverip.org/dtg/vsc/vetted/1/vetting.schema.json",
  "subjectObjectRelationship": null,
  "additionalMembers": {},
  "taskContextRequired": true,
  "minimumIssuerScope": "directed",
  "issuer": "Either a member the community has made eligible to vet, issuing under the member identifier its VMC names, or the community named in object.value.community itself, issuing under its own DID to record a check its operators carried out. A member's eligibility is the community's to confer and to withdraw, and a verifier checks it under community policy rather than inferring it from this statement.",
  "establishes": "That the issuer, a vetter or the community itself, states it carried out the described check on the subject's claimed identity, in the exchange taskContext names.",
  "doesNotEstablish": [
    "that the subject's claimed identity is true",
    "that the vetter was eligible to vet, which is a fact about the community and is checked separately",
    "that the check was competent",
    "that the subject has been admitted to any community; admission is a decision the community records, and this statement is one input to it",
    "that the subject has personhood or any other status the community confers; that is the community's decision, recorded on its membership credential, and this statement is evidence for it"
  ],
  "definedIn": null,
  "governedBy": null,
  "supersedes": null,
  "supersededBy": null
}

```

# Predicate `witnessed/1`

A statement under this predicate is a **verifiable witness credential (VWC)**, one of the two core profiles the [DTG Credentials Core Specification](https://github.com/trustoverip/dtgwg-cred-spec) names. This entry is the profile's normative definition; the specification's *VWC* section states what the profile is and refers here for its members. Verifiers configure against this entry, as the specification's *Predicate Handling* requires.

## What is witnessed

The witness may be a person or a VTA applying the witnessing policies of a VTC: verifying that both parties were present at the same event, say, or that each provided proof of biometric liveness at the time a relationship was formed. Because the meaning of the attestation depends on the conditions under which the witnessing occurred, a statement under this predicate is bound to the trust task exchange in which it was issued: `taskContext` and `taskDigestMultibase` are required.

## One statement per direction

A witnessed exchange of a complete DTG edge is bidirectional: two edge credentials, one in each direction, are formed in one witnessing event, whether two VRCs for a peer-to-peer edge or the two VMCs of a membership edge. For such exchanges the witness SHOULD issue one statement per direction; the obligation is stated normatively in this entry's subject–object relationship. That is what the subject–object relationship makes checkable: the subject is the issuer of the referenced credential, so each statement names one direction of the edge and a verifier holding that credential can confirm it.

The rule is unconditional, and deliberately so. A verifier holding a witness statement and the credential it names cannot tell whether that credential was one half of a reciprocal pair, so a rule that depended on it could not be checked, and two conformant statements naming the same credential could name different parties. Unconditional binding covers the cases that came up in review without a second rule: on a membership edge the member is named by the statement for the member-issued VMC, and if only the grant was witnessed then naming the community is correct, because the member's participation was not observed; a VDC is likewise a grant and an acceptance, so the delegate is named by the statement for the acceptance.

## What the digest binds

`credentialSubject.id` and `taskContext` alone identify the observed party and the exchange, not the edge. Binding a statement to a specific edge therefore requires `object.digestMultibase`: a verifier holding the referenced credential recovers both endpoints of the edge from its `issuer` and `credentialSubject.id` and confirms the exact credential the witness attested to. The binding is only as strong as the verifier's access to that credential; a digest without the credential to hand is an opaque hash, not an identified edge. Issuers and holders presenting a witness statement as evidence of a specific edge should make the referenced credential available alongside it. The digest is computed as the specification's *Digest Encoding* section defines, over the referenced credential excluding its top-level `proof`.

## What this predicate is not

A statement that a party *presented*, *held* or *received* a credential, where the observed party is the referenced credential's subject and its issuer may have been absent, is a different statement with the observed party as its subject. It is a different predicate, defined in this registry rather than expressed by stretching this one: presentation is [`presented/1`](https://registry.trustoverip.org/dtg/vsc/presented/1).

## Notes for implementers

- `witnessContext` is optional and its three members are all optional. Its member set is frozen with this version; a new member is a new version.
- The issuer's correlation scope is `directed` at minimum: a witness's identifier must be recognizable to both parties to the witnessed edge and to the community whose policy the attestation is issued under, so a `pairwise` declaration cannot describe it truthfully.
- The example's identifiers and digests are illustrative. Neither digest is computed from a printed document.
- The specification writes the predicate as `dtg:witnessed`, documentation shorthand for the IRI on this page; on the wire a predicate is always the absolute IRI.

```json
{
  "@context": "https://registry.trustoverip.org/dtg/meta/v1/predicate-context.jsonld",
  "id": "https://registry.trustoverip.org/dtg/vsc/witnessed/1",
  "type": "Predicate",
  "name": "witnessed",
  "version": 1,
  "status": "draft",
  "label": {
    "en": "witnessed",
    "de": "bezeugt",
    "nl": "getuige geweest van"
  },
  "definition": {
    "en": "The issuer attests that it observed the subject issue the credential the object names, under the conditions of a specific trust task exchange."
  },
  "classification": "evidence",
  "weighedBy": "The community whose witnessing policy the attestation is issued under.",
  "objectKind": ["digestMultibase"],
  "subjectObjectRelationship": "credentialSubject.id MUST be the DID of the issuer of the credential object.digestMultibase names, and a verifier holding that credential MUST check that it is. This binds each statement to one direction of the edge it attests. Where one witnessing event forms both edge credentials of a complete DTG edge (two VRCs, or the grant and acknowledgement VMCs of a membership edge), the witness SHOULD issue one statement per direction.",
  "additionalMembers": {
    "witnessContext": {
      "required": false,
      "schema": "https://registry.trustoverip.org/dtg/vsc/witnessed/1/witness-context.schema.json",
      "description": "Context of the witnessing event: a human-readable event name, a session or nonce identifier, and the verification method used."
    }
  },
  "taskContextRequired": true,
  "minimumIssuerScope": "directed",
  "issuer": "A member, or a VTA acting according to VTC policy.",
  "establishes": "That the issuer attests that, in the exchange identified by taskContext, it observed the subject issue the credential whose claims digest to object.digestMultibase.",
  "doesNotEstablish": [
    "that the referenced credential is currently valid or unrevoked; the digest is computed over its claims and excludes both its proof and its status, so the attestation is a statement about those claims at the moment of witnessing",
    "that the referenced credential's claims are true",
    "that the exchange reached its terminal state, which requires the outcome evidence of the specification's Outcome Interpretability rules",
    "that the witness is a member of any community",
    "that any consequential action is authorized"
  ],
  "definedIn": null,
  "governedBy": null,
  "supersedes": null,
  "supersededBy": null
}

```

