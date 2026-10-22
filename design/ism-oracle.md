# ISM Policy Oracle over ToIP

**Status:** design sketch, revision 2, after an adversarial audit (Beads
epic `ToIP-cbk9`). The protocol is not implemented. The ISM-execution
claims were tested with Saxon-HE 12.5; see
[Empirical results](#empirical-results). Claims marked *unverified* still
need testing.

## The idea in one paragraph

The oracle is a generic engine that runs a package's Schematron and XSLT,
and speaks ToIP on the outside. It never names an ISM concept. ODNI's ISM
package is data, pinned by hash in a package credential. A separate
release-policy credential, issued by the governance authority, says which
packages, phases and verdict rules count. The oracle and the release agent
both run inside the holding agency's enclave. A new ISM release means
new credentials; the oracle code does not change.

## What this protects, and what it does not

It protects **markings and their binding to content**. Within the limits
below, an object cannot be released to a reader unless its marking is
consistent under the governing ISM rules, is bound to that exact content,
and the reader holds current access.

It does **not** protect people. Burned sources are a failure of people and
policy, and no protocol fixes them. The design can only reduce how many
parties ever see the linkage between content, markings, classifiers and
readers.

It does **not** establish that a marking is *correct*. ISM rules check
consistency, and ODNI calls them "a valid starter set" (`DesIsmXml.pdf`
§3.1). Marking honesty rests on the classifier's signature and that
classifier's authority, nothing more.

## Governing constraints

These rules remove whole categories of work that a mechanism would
otherwise have to handle.

1. **Carry ISM's own encoding verbatim.** Markings travel as ISM XML, never
   as a JSON mapping of ISM.
2. **Every ISM-specific fact lives in a credential.** That covers package
   layout, entry points, phase names, which phases count, which SVRL roles
   fail, and required attribute constraints. Code holds none of them.
3. **Pin only self-contained trees.** A package credential names one
   directory tree. The oracle refuses to load it unless every
   `document()`, `xsl:import` and `xsl:include` target resolves inside it.
   For ISM that means the **Convenience** zip; the Standalone zip is
   missing 14 dependency files.
4. **The caller never sets stylesheet parameters.** ISM binds its value
   lists to top-level `xsl:param`s such as `releasableToList`. A caller
   who could set them could replace the value lists.
5. **Enclave only.** The oracle, the release agent (PEP), and the clearance
   registries' witnesses run inside the holding agency's accredited
   enclave. Markings and the linkage graph are classified at least at the
   banner level of what they describe. SAR identifiers and SCI
   compartments reveal that programs exist, and who-classified-what across
   many requests is a map. Sources-and-methods material is never evaluated
   by a shared oracle.
6. **Determinism over trust.** The same tree hash, exact engine build and
   configuration, and input digest produce the same normalised result. A
   verifier inside the enclave can re-run any evaluation. The oracle is a
   shared service inside the enclave, not a trust anchor.
7. **Fail closed, everywhere.** Each of these yields no release:
   - an unknown package, policy, phase or SVRL role;
   - an unresolved resource;
   - a missing attestation, or one with a failing verdict;
   - a portion with no marking.

## Credentials

### Package credential

Issued by a **Package Curator** AID that the governance framework names.
The curator's hash is the root of trust, because ODNI does not sign the
zip.

| Attribute | V2022-NOV value |
|---|---|
| `packageName`, `packageVersion` | `ISM`, `2021-NOVr2022-NOV` |
| `zipSha256` | `0d6764205fe1a3158ba257a3143effe63f8129e22432d6405e117dc7f09fc7f2` (Convenience) |
| `treeManifest` | `ISM/manifest.md5` (verified on load) |
| `schematron` | `Schematron/ISM/ISM_XML.sch` |
| `allXsl` | `Schematron/ISM/ISM_XML.xsl` (all rules) |
| `phaseXsl` | `Schematron/ISM/ISM_XML-{phase}-phase.xsl` (**optional**; ISM V13, 2016, ships no phases) |
| `xsd` | `Schema/ISM/IC-ISM.xsd` (plus `IC-ARH.xsd` and `IC-NTK.xsd` when those namespaces are used) |
| `desVersionAttr`, `desVersionPattern` | `ism:DESVersion`, `^202111.202211(-.{1,23})?$` (from rule ISM-ID-00300) |
| `entryPoints` | list of `{id, stylesheet, initialMode, contextXPath, errorPatterns}` for rendering |
| `xsltVersion`, `releaseClass` | `2.0`, `Public` |

The `entryPoints` list is the only thing a `transform` request can name.
ISM's rendering XSLs are libraries driven by modes (`ism:banner`,
`ism:portionmark`), not stand-alone stylesheets. A rendering that emits
strings such as "UNABLE TO DETERMINE CLASSIFICATION MARKING" is an
error. Those strings go in `errorPatterns`, which is data.

**Succession.** A new ISM release is a new credential. It carries an `NI2I`
edge to its predecessor and does not revoke it, because documents marked
under an older `DESVersion` still need the old one. A curator revokes a
package credential only when that credential is wrong. A classified-network
deployment issues its own credential for the full package. The public CVEs
contain only `(U)` values, and `CVEnumISMSAR` is empty.

### Release-policy credential

Issued by the **governance authority**, not the curator, and not chosen by
the requester. It closes the downgrade path (C2/H2) and holds every
judgement about which ISM results count.

| Attribute | Purpose |
|---|---|
| `acceptedPackages` | Package-credential SAIDs the PEP accepts. The requester's choice is advisory. |
| `requiredPhases` | `#ALL`. One phase passing does not mean the document is valid. `PORTION` and `ROLLUP` together cover 271 of 420 patterns. INFRASTRUCTURE, ROLLDOWN and TYPECHECK each passed every invalid probe. BANNER passed an unknown SCI control. |
| `failOn` | e.g. `{attr: "role", values: ["error", "fatal"], unknown: "fail"}`. Warnings come out as `svrl:failed-assert` too, and ISM changed one rule from error to warning between versions. |
| `requireXsd` | Whether schema validation must pass. |
| `assertions` | XPath booleans over the skeleton, each of which must be true. For ISM: `compliesWith` contains `USGov` (it gates 173 rule files, via `ISM_USGOV_RESOURCE`); no content portion carries `excludeFromRollup="true"`. |
| `createDateAttr` | `ism:createDate`. Must equal the date of the document ACDC's issuance, because deprecation is judged against it and a producer could backdate it. |
| `trustedOracles`, `trustedClassifiers` | AIDs, or the schema SAIDs of the authority credentials those AIDs must hold. |

## Labelled content

- **Portions.** Each portion is a private ACDC. Its attributes carry the
  content and the portion's own ISM marking as an XML fragment. The
  portion's SAID therefore commits to both, so a portion cannot be
  re-marked by wrapping it in a new document (C1).
- **The document.** It is an ACDC whose edges point to its portions (`o:
  NI2I`). Its attributes carry the skeleton in exclusive C14N:
  - Every element and attribute in the `urn:us:gov:ic:ism`,
    `urn:us:gov:ic:ntk` and `urn:us:gov:ic:arh` namespaces is kept
    verbatim, **text included**.
  - Only host-element text is replaced, with that portion's SAID.

  Some rules read the text of `ntk:ProfileDes`, `ntk:AccessPolicy`,
  `ntk:AccessProfileValue` and `ism:NoticeText`, so replacing that text
  breaks validation (ISM-ID-00493). Host element names don't matter,
  because no rule context depends on them. As a result, `ism:NoticeText`,
  which is free prose, is visible to the oracle.
- **Issuer.** Both are issued by a **classifier** AID holding an authority
  credential that chains to an original classification authority, and both
  are anchored in the classifier's KEL. A SAID is a digest; the signature
  or KEL anchor is what binds authorship.
- **Consistency check (PEP).**
  - The set of portion SAIDs in the skeleton equals the set of edge `n`
    values, with no duplicates.
  - Each skeleton portion's `ism:*` attributes equal the marking inside
    that portion's ACDC.
  - A portion with no marking is withheld.

## Oracle protocol (Trust Tasks over TSP)

**Type URIs** are private, on a domain the curator controls, until they are
registered: `https://<curator-domain>/spec/policy-oracle/{discover,evaluate,transform}/0.1`.
Responses use `#response`. Request documents carry `proof`, because no
Trust Tasks TSP binding yet permits omitting it.

| Task | Request `payload` | Response `payload` |
|---|---|---|
| `discover` | `{ package }` | `{ phases, entryPoints }`, read from the credential and package |
| `evaluate` | `{ package, policy, document }` | `{ result, svrl, attestation }` |
| `transform` | `{ package, policy, document, entryPoint }` | `{ output, attestation }` |

- **`package` and `policy`** are required credential SAIDs. The oracle
  evaluates exactly what is named, or returns `trust-task-error` with
  `policy-oracle:unknownPackage` or `policy-oracle:unknownPolicy`. The
  attestation's edges let any verifier detect substitution. Trust Tasks'
  `extCritical` plays no part, because it covers only `ext` namespaces.
- **`document`** is the compact document ACDC. The oracle verifies its SAID
  and extracts the skeleton itself, so there is no free-standing skeleton
  that could diverge from what is attested (H3).
- **`result`** is `noViolationsFound` or `violationsFound`, worked out under
  the policy's `requiredPhases` and `failOn`. It is never called "pass":
  the oracle cannot certify that a marking is correct.
- **`transform`** first requires a `noViolationsFound` evaluation of the
  same document under the same policy. An output matching an
  `errorPatterns` entry is an error.

### Execution rules

- The URI resolver serves only the verified tree. Any other read is a hard
  error, never an empty document; an empty document would quietly turn off
  the deprecation checks.
- A document containing a DOCTYPE is rejected.
- `phase` values must match the declared IDs exactly before they go into
  `phaseXsl`; `#ALL` maps to `allXsl`.
- No caller-supplied `xsl:param`s.
- There are CPU, memory and input-size limits.
- `xsl:result-document` and engine extension functions are disabled. The
  ISM package uses neither.
- **For determinism:**
  - Inputs are passed as streams with no system ID, so SVRL's
    `document-uri`-derived `@document` comes out empty.
  - The exact engine build and configuration are recorded.
  - The default language is pinned (ISM's date rendering uses `[MNn]`).

  Under those conditions, raw SVRL from ODNI's compiled XSL is
  byte-identical across runs and directories. The attestation covers that
  raw SVRL. A verifier who compiles `ISM_XML.sch` fresh gets the same set
  of failed assertions (rule ID plus location) but different SVRL bytes.
  Such a verifier compares that set, not the digest.
- The oracle keeps compiled stylesheets in a long-running process. A cold
  JVM per request costs about 3 s; warm evaluation takes about 50–70 ms for
  the full rule set.
- **Conformance needs a negative corpus.** ODNI ships no invalid examples
  for the Schematron rules; its XSPEC suite covers only rendering. Oracle
  conformance tests need invalid documents whose expected failures come
  from ODNI's rule text, not from the oracle under test.

## Attestations

Each attestation has its own schema. Both are kept by the PEP inside the
enclave and never published.

**Label evaluation** (issued by the oracle):
- Edges (`o: NI2I`) to the package credential, the policy credential and
  the document ACDC.
- Attributes: phases run, `result`, the normalised SVRL digest, the XSD
  result, the engine build and configuration, and `issuedAt`.

**Access decision** (issued by the PEP for one reader and one portion):
- Edges to the label evaluation, the portion ACDC, and each clearance or
  access ACDC it relied on.
- Attributes: the reader's AID, the TEL state and sequence number seen for
  each clearance, the result of the reader-versus-marking evaluation,
  `issuedAt`, and a short `expiresAt`.

The PEP re-reads TEL state at release time. A decision attestation is never
reused for another reader, another portion, or after it expires (C3).

## Clearances and access

- **Read-in.** An access ACDC is issued by the security officer's AID to the
  reader's AID, chained to the adjudicating authority. The reader accepts
  it with an IPEX `admit` signed by their own key. Unlike a wet signature,
  that acknowledgement is non-repudiable and tied to the exact grant.
- **Debrief.** The security officer revokes the ACDC in its TEL. The
  revocation is the debrief record.
- **Current status is TEL state.** The design uses no TRQP for this.
  TRQP answers are unsigned JSON over HTTPS, so they are not evidence that
  can go into an attestation.
- **Rosters stay private.** A clearance TEL is a roster of who is read into
  what. Clearance and access ACDCs are private, their registries' witnesses
  run inside the enclave, and only the PEP checks status.
- **Comparing reader to marking** belongs to ODNI's access-control packages
  (ISM.ACES, NTK). They run through the same `evaluate` task under their
  own package credentials. *Unverified:* those packages have not been
  inspected. Until an accepted ACES/NTK attestation exists, the PEP denies.

## Release (IPEX)

1. The reader sends `apply`.
2. If the PEP lacks a current label evaluation with `noViolationsFound` and a
   current access decision for that reader and portion, it replies `spurn`.
   The reader keeps only the compact SAID: "you don't get to read this
   part".
3. Otherwise:
   - The PEP sends `offer`, the metadata or compact variant plus Rules.
   - The reader sends `agree`.
   - The PEP sends `grant`, the full disclosure, in a confidential TSP
     payload to the reader's VID. In routed mode that payload is end-to-end
     encrypted.
   - The reader sends `admit`.

If the required evaluation over the whole document fails, nobody can state
its true classification, so every portion is withheld.

**Denials say nothing to the reader.** A `spurn` carries no reason, because
"you lack SI-G" would itself reveal a compartment. The PEP sends the
document owner or security officer a notice that names the reader and the
portion. They decide whether a read-in is warranted.

## When ISM changes

| Change | What changes here |
|---|---|
| New or retired CVE values, rules or phases | New package credential; the release policy accepts it. No code change. |
| New `DESVersion` | New package credential with a new `desVersionPattern`. Old documents keep validating against the old credential. |
| Files moved, or phases dropped (as in V13) | New credential values (`allXsl`, `phaseXsl` absent). The policy uses `#ALL`. No code change. |
| Rule severity changes (error to warning) | The `failOn` value in the release policy, which is data. |
| New dependency package | Pin the new Convenience tree. The load-time resolution check catches an incomplete tree. |
| Move to XSLT 3.0 | Oracle needs an engine that supports it. **Known ceiling.** |
| XSD validation | Saxon-HE cannot validate against XSD, so a second validator is needed. **Known ceiling.** |
| ODNI drops Schematron and XSLT | This design does not survive. **Known ceiling.** |

## The meta-spec

Generalised, this is a **Policy Package Oracle** spec in four parts:

1. A package credential schema.
2. A release-policy credential schema.
3. The three Trust Task types.
4. The two attestation schemas.

Only the credential *values* are specific to ISM. The spec fits any policy
published as self-contained Schematron and XSLT. STANAG 4774 and NIEM are
possible targets; *unverified* whether NATO ships Schematron for 4774.

## Empirical results

**Setup:** Saxon-HE 12.5 with xmlresolver 5.2.2, on OpenJDK 21. The
evaluation used `ISM_XML.xsl` from the V2022-NOV Convenience tree
(`spec/ism-convenience/ISM/`), and ran 2026-10-21. The scripts live in the
session scratchpad, not in this repo.

The examples, invalid-input and skeleton-pass rows were run on the
Convenience tree. The ntk-text, determinism, SchXslt and locked-down rows
were run during the audit on a hand-assembled tree. That tree was the
Standalone package plus the ISMCAT, AUTHCAT, MN, ROLE and USAgency
Standalone zips, with a stub LIC value list. It has not yet been re-run on
the Convenience tree.

| Test | Result |
|---|---|
| Standalone zip alone | Every document fails: `FODC0002` on `CVE/ISMCAT/CVEnumISMCATOwnerProducer.xml`. Constraint 3 exists because of this. |
| ODNI examples, Convenience tree | 52 of 52 run with 0 errors and 0 failed assertions. |
| Invalid inputs (banner below its portions, no `ownerProducer`, classification `X`, SCI `ZZZ`, SAR `FOO`) | All 7 caught. Unknown values are rejected by value-list lookup (e.g. ISM-ID-00267). |
| Skeletons (SAID text, renamed host elements, flattened, ARH removed) | Pass, with 0 failed assertions. Replacing ntk text fails (see the skeleton rule above). |
| Determinism | Same bytes across repeat runs and different directories. No clock, environment or random calls anywhere in the package. |
| Shipped phase XSL vs SchXslt 1.10.1 compile of `ISM_XML.sch` | 150 of 150 pairs give the same failed assertions once locations are normalised. Raw SVRL bytes differ. |
| Locked-down run (no network, `file:` only) | Byte-identical output. The `jar:`-only negative control fails, so the restriction is enforced. |

## Open questions

1. **Accreditation.** A correct oracle is not an accredited one. That is out
   of scope here.
2. **ACES and NTK packages.** Do they fit the same `evaluate` shape for
   comparing a reader to a marking?
3. **Linkage over time.** Within the enclave, a portion SAID is stable for
   life, so access-decision history is itself sensitive. Retention policy
   for attestations is unspecified.
