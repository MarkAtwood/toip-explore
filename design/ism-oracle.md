# ISM Policy Oracle over ToIP

**Status:** design sketch, for exploration. Nothing here is implemented or
tested. Claims marked *unverified* need a Saxon run before anyone relies
on them.

## The idea in one paragraph

The oracle is a generic engine that runs a package's Schematron and XSLT,
and speaks ToIP on the outside. It never names an ISM concept. ODNI's ISM
package is data, pinned by hash in a "package credential" (an ACDC). Requests
arrive as Trust Task documents over TSP. Each request names a package hash,
an operation, and an ISM XML document that carries only markings. The answer
is an ACDC attestation that anyone holding the same package can reproduce.
When ODNI ships a new ISM version, a curator issues a new package
credential. No oracle code changes.

## Governing constraints

These rules remove whole categories of work that a mechanism would
otherwise have to handle.

1. **Carry ISM's own encoding verbatim.** Labels travel as ISM XML, not as
   a JSON mapping of ISM. Mapping code would have to follow ISM's structure
   and would reopen the round-trip problem. Carrying the XML verbatim
   deletes both.
2. **Operations come from the package, not the oracle.** ODNI already splits
   its rules into named Schematron phases (`BANNER`, `PORTION`, `ROLLUP`,
   `ROLLDOWN`, `VALUECHECK`, `TYPECHECK`, `STRUCTURECHECK`, `INFRASTRUCTURE`,
   `NON_INFRASTRUCTURE` in V2022-NOV). It ships each one pre-compiled as
   `Schematron/ISM/ISM_XML-<PHASE>-phase.xsl`. The oracle reads the phase
   IDs from `ISM_XML.sch` and treats each one as an opaque string.
3. **The oracle sees markings, never content.** The submitted document is a
   *skeleton*: the real structure and every `ism:*` attribute, with each
   portion's text replaced by that portion's ACDC SAID. Classified text never
   reaches the oracle.
4. **Determinism over trust.** Package hash, engine and version, and input
   digest fix the output. The oracle is a convenience for thin clients, not
   a trust anchor. A verifier with Saxon can skip it entirely.
5. **Fail closed, everywhere.** An unknown package, an unknown phase or a
   failed assertion produces no positive attestation. No attestation means
   no release.

## Parts

### 1. Package credential (ACDC)

Issued by a **Package Curator** AID: whoever the ecosystem's governance
framework trusts to republish ODNI packages. A new ISM release means a new
credential. Superseding an old one is a normal ACDC revocation in its
registry.

| Attribute | Example (this repo) |
|---|---|
| `packageName` | `ISM` |
| `packageVersion` | `2021-NOVr2022-NOV` (from `ISMpackage.properties`) |
| `zipSha256` | `29362fedb43f85b2d453977d76151bfec81875c9fbb60cd46867eb30004eea81` |
| `sourceUrl` | ODNI `.../Dec2022/ISM/ISM-Public-Standalone.zip` |
| `schematron` | `Schematron/ISM/ISM_XML.sch` |
| `phaseXsl` | `Schematron/ISM/ISM_XML-{phase}-phase.xsl` |
| `xsltVersion` | `2.0` |
| `releaseClass` | `Public` (the public CVEs omit classified values; see below) |

`schematron` and `phaseXsl` are the only facts about package layout, and
they live in data. If ODNI renames a file, the curator issues a new
credential; nobody edits code. A classified-network deployment issues its
own credential for the full package. The oracle code is the same.

### 2. Labelled content

- Each portion is a private ACDC. Its attribute section is blinded, and its
  content is encrypted to the recipient over TSP.
- The document is an ACDC whose edges point to its portions. Its attributes
  carry the skeleton ISM XML (exclusive C14N) as a string.
- The portion markings in the skeleton are the authoritative label. Because
  the document ACDC's SAID covers the skeleton, the label is cryptographically
  bound to the content set. That is the job STANAG 4778 does for NATO labels.

### 3. Oracle protocol (Trust Tasks over TSP)

There are three task types. None of them names an ISM concept.

| Type URI (illustrative) | Request `payload` | Response `payload` |
|---|---|---|
| `…/policy-oracle/discover/0.1` | `{ package }` | `{ phases: [...], stylesheets: [...] }`, read from the package |
| `…/policy-oracle/evaluate/0.1` | `{ package, phase, document }` | `{ verdict, svrl, attestation }` |
| `…/policy-oracle/transform/0.1` | `{ package, stylesheet, document }` | `{ output, attestation }` |

The fields mean:

- `package` is the package credential's SAID.
- `phase` is any phase ID the package declares, or `#ALL`.
- `stylesheet` is a path inside the package, such as
  `XSL/ISM/IC-ISM-DOD-Rendering.xsl` for banner rendering. Only files inside
  the pinned package may be named.
- `verdict` is `pass` only when the SVRL report contains no failed
  assertion.

The requester marks its package pin with Trust Tasks' `extCritical`. An
oracle that would silently substitute a different package version must then
reject the request with `unsupportedExtension`. That is the spec's existing
"reject if not understood" rule, used for exactly that purpose.

### 4. Attestation (ACDC)

Issued by the oracle's AID.

- **Edges:** the package credential, and the document ACDC (or the
  skeleton digest when there is no document ACDC).
- **Attributes:** the phase or stylesheet, the verdict, the SVRL or output
  digest, and the engine identity (for example `Saxon-HE 12.x`).

The engine version belongs in the attestation because it is part of what
determines the result. Any verifier can re-run the evaluation and compare
digests.

### 5. Access decision and release

- **PDP (the oracle).** Per portion, a reader may receive it only when
  `PORTION` and `ROLLUP` pass and the reader's attributes meet the marking.
- **Reader attributes.** Clearance and SCI or compartment access are ACDCs
  chained to the adjudicating authority. Registry facts ("does AID X hold
  access Y right now?") come from TRQP's `/authorization` query, with
  `entity_id` set to the reader's AID and `authority_id` to the adjudicating
  authority.
- **Comparing reader to marking.** That comparison is not ToIP's job. It
  belongs in ODNI's access-control packages (ISM.ACES, NTK), run through the
  same `evaluate` task with a different package credential. *Unverified:* I
  have not inspected the ACES or NTK packages.
- **PEP (a release agent).** It discloses a portion through IPEX only when
  it holds a positive attestation for that reader and portion. Otherwise the
  reader gets the portion's SAID and nothing else: "you don't get to read
  this part". If `ROLLUP` fails, nobody can state the document's true
  classification, so the whole document is withheld.

## When ISM changes

| Change | What changes here |
|---|---|
| New or retired value-list (CVE) values | New package credential. No code change. |
| New or changed rules | New package credential. No code change. |
| New phase | New package credential; `discover` lists the phase. No code change. |
| New `DESVersion` | The skeleton carries `ism:DESVersion` and the requester pins the matching package. Old attestations stay valid against the old package SAID. |
| Files renamed or moved in the package | New package credential with new `schematron` and `phaseXsl` values. No code change. |
| Move to XSLT 3.0 | Oracle needs an engine that supports it. **Known ceiling**: the one real code dependency. |
| ODNI drops Schematron and XSLT entirely | This design does not survive. **Known ceiling.** |

## The meta-spec

Nothing above is specific to ISM except the values in the package
credential. Generalised, it is a **Policy Package Oracle** spec in three
parts:

1. A package credential schema.
2. The three Trust Task types.
3. An attestation schema.

It fits any policy published as Schematron and XSLT. Possible targets are
STANAG 4774 confidentiality labels and NIEM; *unverified* whether NATO ships
Schematron for 4774.

## Open questions (resolve with a Saxon run)

1. **Do skeletons validate?** ISM rules key off `ism:*` attributes, which
   suggests a skeleton with arbitrary host elements will validate.
   *Unverified.* Test it against `ISM/Examples/`.
2. **Is SVRL output deterministic?** Check whether it contains timestamps or
   unordered output. If it does, attest to a normalised SVRL.
3. **Are the shipped phase XSLs equivalent to compiling `ISM_XML.sch`
   fresh?** Use ODNI's compiled forms either way, so the oracle has no
   Schematron compiler dependency.
4. **Public versus full package.** The public CVEs contain only `(U)`
   values, and `CVEnumISMSAR` is empty. Against the public credential, any
   SAR marking or classified SCI compartment fails closed. That is correct
   behaviour, but it makes the public package useful only for unclassified
   testing.
5. **Accreditation.** A correct oracle is not an accredited one. That is out
   of scope here.
