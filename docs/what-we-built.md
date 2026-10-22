# What we built: Trust over IP, drafted into guarding classified documents

**Short version:** we took Trust over IP, a set of standards built so that
people and organisations can trust each other *without* a central
authority, and designed a way to use it to enforce US government
**classification markings**: `TOP SECRET`, code-word compartments,
"no foreign nationals", need-to-know. That is close to the most
centralised, top-down access control there is. It's the opposite of what
ToIP was built for, and as far as we can tell it works anyway, while
following the specs to the letter.

In practice the design does three things:

- It checks that a document's classification markings are consistent,
  using the government's own published rule set, run unchanged.
- It seals each marking to its paragraph so nobody can swap it.
- It releases each paragraph only to readers who are cleared for it right
  now.

When the government updates its rules, the software doesn't change. You
load the new rules file and re-sign one record.

Nothing is running in production. What exists is a design document that
four independent reviewers tried to break, the government's rule files
saved in our repo, and test runs showing that those rules behave the way
the design needs.

## The problem, without the jargon

Think of a document as a stack of paragraphs. Each paragraph has a sticker
saying who may read it: "anyone", "staff only", or "staff on Project X
only". The whole document carries a summary sticker at the top, and the
summary has to be at least as strict as the strictest paragraph. Some
stickers combine in odd ways: two "may share with" lists combine by
narrowing, not by adding up.

The US intelligence community does exactly this, at scale, with
"classification markings". The labels are formal codes such as `TOP SECRET`,
`SI` and `NOFORN`. The rules for which combinations are legal, and how
paragraph labels combine into the summary, fill a thick manual.

The government publishes a machine-readable version of those rules, called
**ISM** (Information Security Marking). It contains:

- **Lists of allowed values:** every legal label code.
- **A rule checker:** about 300 rules, written in a standard XML
  rule language (Schematron) that compiles to XSLT programs. Feed it a
  labelled document and it reports every rule the document breaks.
- **A label printer:** code that turns the labels into the text banners
  you see at the top and bottom of each page.

So the rules already exist as code. What's missing is a way to:

1. prove *who* applied a label and that it hasn't been tampered with,
2. prove *which version* of the rules a document was checked against,
3. decide, for one particular reader, whether they can see each paragraph,
   and
4. keep doing all that when the government revises its rules.

## Where ToIP comes in

**Trust over IP (ToIP)** is a family of open standards for verifiable
identity and signed digital credentials. In everyday terms:

- **KERI** gives every person, office and service a cryptographic identity
  that can rotate its keys without becoming a different identity.
- **ACDC** is a signed, tamper-evident data record that can link to other
  records, like a notarised form that cites other notarised forms. It
  supports revealing only some fields.
- **TSP** is an encrypted messaging channel between those identities.
- **IPEX** is a short "may I have it? / here it is / received" handshake
  for handing over a credential.

We use ToIP as the plumbing and the government rule files as the brains.

## The joke

ToIP's founding story is decentralisation and human agency. You choose whom
to trust, you hold your own credentials, you disclose only what you want
to, and governance is open and shared. This design keeps every mechanism
and inverts every value:

| ToIP was built for | Here it is used for |
|---|---|
| Peers choosing whom to trust | A governance authority deciding for everyone; the requester's choice is "advisory" |
| Credentials you hold and present wherever you like | Clearances issued to you, revoked by someone else, and checked only inside a sealed enclave |
| Selective disclosure, so *you* can hide things from others | Selective disclosure, so others can hide things from *you* |
| Public witnesses keeping everyone honest | Witnesses locked inside a classified enclave, because the list of who is cleared for what is itself secret |
| Open, verifiable, explainable decisions | Being refused with no reason given, because the reason ("you lack `SI-G`") would itself be classified |
| Getting rid of the paper trail | Replacing a filing cabinet of signed nondisclosure forms with a cryptographically perfect one |

The best part is that none of it bends the specs. An independent review
against the ToIP standards made the design *more* compliant, not less. It
is a fully compliant use of the stack that its authors would never have
chosen.

## How it works

1. **The rules become a pinned file.** Someone the organisation trusts
   (the "curator") downloads the government's rules package, records its
   fingerprint (a SHA-256 hash), and signs a record that says "this exact
   file is ISM version 2022-NOV". Changing one byte of the rules changes
   the fingerprint, so nobody can substitute rules quietly.
2. **A policy record says what counts.** A separate signed record from the
   organisation's governance body says which rule versions are accepted,
   that *all* rules must run, which problems count as failures, and a few
   extra checks. The person asking for a check does not get to choose.
3. **Labels are sealed to content.** Each paragraph is its own signed
   record, and its label sits inside that record. Moving a secret paragraph
   into a new document with a softer label breaks the signature.
4. **The checker never sees the secrets.** It receives a "skeleton": the
   document's structure and labels, with each paragraph's text replaced by
   its fingerprint.
5. **Results are signed and reproducible.** The checker signs its result,
   recording the rule-file fingerprint and the exact software version. Anyone
   with the same files can re-run the check and get byte-identical output,
   so you don't have to trust the checker.
6. **Release is per reader, per paragraph.** A "release agent" hands a
   paragraph over only if three things hold: the document checked out, the
   reader currently holds the right access, and that decision was made for
   *this* reader and *this* paragraph a short time ago. Anyone else gets
   the paragraph's fingerprint and nothing more: proof something is there,
   with no hint of what it is.
7. **Access is a revocable credential.** Granting someone access to a
   project issues them a signed credential, and they sign to accept it.
   Removing access revokes it. Today that process runs on paper forms and a
   central database.

When the government ships new rules, the curator signs a record for the new
file and the governance body accepts it. That's the whole upgrade.

## What we proved, and what we didn't

**Tested and working**, using the government's published files and the
Saxon XSLT engine:

- All 52 of the government's example documents pass the rules.
- All 7 deliberately broken documents are caught. These included a
  summary label weaker than a paragraph, a missing owner, and invented label
  codes.
- Skeleton documents, with text swapped for fingerprints, are checked the
  same as real ones. The one exception is a few label-related text fields
  that must be kept.
- Same input, same output, byte for byte, across runs and machines.
- The checker works with networking switched off and file access confined
  to the rules folder.

**Found by the reviewers and fixed in the design:**

- A label could be moved onto different content.
- The submitter could switch off whole groups of rules using flags inside
  the document itself.
- A "yes" result could be replayed for a different reader.
- The government's "standalone" rules download is missing files it needs
  in order to run.

**Not done:**

- No running service exists.
- Nothing was tested against real classified rule sets. The public files
  contain only the unclassified label codes; the secret ones are left out.
- Nobody has certified any of this for real use, and certification is a
  bigger hurdle than the engineering.

## Why it might matter outside government

Nothing in the core is specific to ISM. The reusable idea is this: **treat
someone else's rulebook as a fingerprinted, signed file, run it unchanged,
and sign reproducible results.** That fits any domain whose rules are
published in machine-readable form and change over time. Examples include
export controls, medical-record consent rules, and data-residency policy.

The companion document,
[policy-package-oracle-spec.md](policy-package-oracle-spec.md), writes that
idea up as a draft specification in ToIP's format.

## The caveat that matters most

This protects *labels and who sees what*. It does not protect *people*.
When sources or partners get burned, that comes from human and political
decisions, and software can't prevent it. The design tries to keep the map
of who-labelled-what and who-read-what inside the owning organisation, but
it can only reduce exposure, not remove it.
