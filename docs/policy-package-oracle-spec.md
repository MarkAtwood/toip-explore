Policy Package Oracle Specification
==================

**Specification Status**: v0.1 Exploratory Draft (not a ToIP deliverable)

**Latest Draft:**

This repository, `docs/policy-package-oracle-spec.md`

**Editors:**

- Mark Atwood

**Contributors:**

**Participate:**

~ Not yet published

------------------------------------

## Status of This Memo

This is an exploratory draft. No ToIP working group has reviewed it, and it
has no standing as a ToIP specification. It generalises the design in
`design/ism-oracle.md` and is meant to start discussion.

## RFC 2119

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY" and
"OPTIONAL" in this document are to be interpreted as described in
[RFC2119] and [RFC8174] when, and only when, they
appear in all capitals, as shown here.

## Foreword

Many domains publish their policy as machine-readable rules. Governments,
standards bodies and regulators revise those rules on their own schedules.
Systems that re-implement the rules drift from them, and systems that
embed them need a code release for every revision.

This specification takes another approach. It treats a published rule
package as content-addressed data, executes it unchanged, and expresses
everything around it with ToIP mechanisms:

- package identity and governance, as credentials;
- requests, as Trust Tasks;
- results, as attestations;
- release, as an IPEX exchange.

## Introduction

A Policy Package Oracle evaluates labelled objects against a
[[ref: policy package]] that a [[ref: package credential]] pins by hash,
under rules set by a [[ref: release-policy credential]]. Its results are
[[ref: evaluation attestations]] that any party holding the same package
and engine can reproduce. A [[ref: release agent]] combines those results
with the reader's current entitlements to release each part of an object
to each reader, or to withhold it.

The oracle contains no knowledge of any particular policy domain.
Everything specific to a domain is a value in a credential.

## Scope

**In scope:**

- the package credential and release-policy credential schemas;
- the structure of labelled objects;
- three Trust Task types (`discover`, `evaluate`, `transform`);
- execution requirements;
- attestation schemas;
- the release exchange.

This version covers policy packages expressed as
[ISO-19757-3] Schematron with an XSLT 2.0 query binding, and
XSLT 2.0 [XSLT20] stylesheets.

**Out of scope:**

- the semantics of any policy domain;
- accreditation and certification;
- key management beyond what [KERI] specifies;
- confidentiality mechanisms beyond [TSP].

## Normative references

- **[KERI]** ToIP, *Key Event Receipt Infrastructure (KERI)* v1.1.

- **[ACDC]** ToIP, *Authentic Chained Data Containers (ACDC)* v1.1, including IPEX.

- **[CESR]** ToIP, *Composable Event Streaming Representation (CESR)* v1.1.

- **[TSP]** ToIP, *Trust Spanning Protocol (TSP) Specification*, Release 1.0.

- **[TRUST-TASKS]** ToIP DTGWG, *Trust Tasks*, Working Draft 0.7.0.

- **[ISO-19757-3]** ISO/IEC 19757-3, *Document Schema Definition Languages (DSDL), Part 3: Rule-based validation, Schematron*.

- **[XSLT20]** W3C, *XSL Transformations (XSLT) Version 2.0*.

- **[EXC-C14N]** W3C, *Exclusive XML Canonicalization Version 1.0*.

- **[RFC2119]** IETF, *Key words for use in RFCs to Indicate Requirement Levels*.

- **[RFC8174]** IETF, *Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words*.

## Terms and Definitions

[[def: policy package, policy packages]]
~ A published, self-contained directory tree of rules, value lists and
  stylesheets for one policy domain, distributed as a single archive.

[[def: package credential, package credentials]]
~ An ACDC, issued by a [[ref: package curator]], that pins one
  [[ref: policy package]] by archive hash and records every fact about its
  layout as data.

[[def: package curator]]
~ An AID that the governance framework authorises to issue
  [[ref: package credentials]].

[[def: release-policy credential, release-policy credentials]]
~ An ACDC, issued by a [[ref: governance authority]], that states which
  [[ref: package credentials]] are accepted and which evaluation results
  permit release.

[[def: governance authority]]
~ The AID that issues [[ref: release-policy credentials]] for a deployment.

[[def: labeller]]
~ An AID authorised to apply labels, which issues
  [[ref: labelled objects]] and [[ref: labelled parts]].

[[def: labelled object, labelled objects]]
~ An ACDC whose edges reference its [[ref: labelled parts]] and whose
  attributes carry its [[ref: skeleton]].

[[def: labelled part, labelled parts]]
~ A private ACDC carrying one unit of content and that unit's own label.

[[def: skeleton]]
~ The XML form of a [[ref: labelled object]]. It keeps all policy-namespace
  markup verbatim, and replaces the text of each host element with the
  SAID of the corresponding [[ref: labelled part]].

[[def: oracle]]
~ An AID that executes [[ref: policy packages]] in response to Trust
  Tasks and issues [[ref: evaluation attestations]].

[[def: evaluation attestation, evaluation attestations]]
~ An ACDC, issued by an [[ref: oracle]], that records the result of one
  evaluation of one [[ref: skeleton]].

[[def: access-decision attestation, access-decision attestations]]
~ An ACDC, issued by a [[ref: release agent]], that records a release
  decision for one reader and one [[ref: labelled part]].

[[def: release agent]]
~ The party that holds [[ref: labelled parts]] and discloses them through
  IPEX. It acts as the policy enforcement point.

[[def: entitlement credential, entitlement credentials]]
~ An ACDC, issued to a reader by a status authority, that grants
  eligibility for some class of labelled content. Its current state is its
  TEL state.

[[def: deployment boundary]]
~ The accredited environment inside which the [[ref: oracle]], the
  [[ref: release agent]] and the witnesses of entitlement registries
  operate.

## 1 Architecture

Seven roles participate. One party MAY hold several roles, except that an
[[ref: oracle]] MUST NOT be the [[ref: labeller]] of any object it
evaluates.

| Role | Issues | Consumes |
|---|---|---|
| Package curator | Package credentials | Published policy packages |
| Governance authority | Release-policy credentials | Package credentials |
| Labeller | Labelled objects and parts | Its own labelling authority credential |
| Oracle | Evaluation attestations | Package and release-policy credentials, labelled objects |
| Release agent | Access-decision attestations, IPEX `grant` | All of the above, entitlement TEL state |
| Status authority | Entitlement credentials and their TEL events | |
| Reader | IPEX `apply`, `agree`, `admit` | Disclosed parts |

## 2 Policy packages

1. A [[ref: policy package]] MUST be self-contained. Every
   `xsl:import`, `xsl:include`, `document()` and `doc()` target reachable
   from a declared entry point MUST resolve to a file inside the tree.
2. An oracle MUST verify self-containment when it loads a package, and
   MUST refuse a package that fails it.
3. A curator SHOULD prefer the publisher's bundled distribution, which
   includes dependencies, over a minimal one that needs other archives
   assembled alongside it.

## 3 Package credential

A [[ref: package credential]] MUST contain the attributes below.

| Attribute | Req. | Meaning |
|---|---|---|
| `packageName`, `packageVersion` | MUST | Publisher's identifiers |
| `archiveSha256` | MUST | SHA-256 of the archive as published |
| `sourceUri` | MUST | Publisher's URI for the archive |
| `treeManifest` | MAY | Path to a publisher manifest to verify on load |
| `schematron` | MUST | Path to the top-level Schematron |
| `allXsl` | MUST | Path to the compiled stylesheet covering all patterns |
| `phaseXsl` | MAY | Path template with a `{phase}` token, for per-phase compiled stylesheets |
| `xsd` | MAY | Schema paths |
| `policyNamespaces` | MUST | Namespace URIs whose markup a skeleton keeps verbatim, text included |
| `versionAttr`, `versionPattern` | MAY | Attribute and regular expression that identify which package version a skeleton targets |
| `entryPoints` | MAY | List of `{id, stylesheet, initialMode, contextXPath, errorPatterns}` |
| `xsltVersion` | MUST | Required XSLT version |

Succession and revocation:

1. A curator MUST NOT revoke a package credential only because a newer
   package exists.
2. A successor credential SHOULD carry an edge to its predecessor with
   operator `NI2I`.
3. A curator MUST revoke a package credential whose recorded values are
   wrong.

## 4 Release-policy credential

| Attribute | Req. | Meaning |
|---|---|---|
| `acceptedPackages` | MUST | SAIDs of the accepted package credentials |
| `requiredPhases` | MUST | Phase IDs, or `#ALL` |
| `failOn` | MUST | `{attr, values, unknown}`. An SVRL failed assertion whose `attr` value is in `values` is a violation. `unknown` MUST be `fail`. |
| `requireXsd` | MUST | Boolean |
| `assertions` | MAY | XPath 2.0 boolean expressions that MUST each be true over the skeleton |
| `createDateAttr` | MAY | Attribute that MUST equal the date of the labelled object's issuance |
| `trustedOracles`, `trustedLabellers` | MUST | AIDs, or the schema SAIDs of the authority credentials those AIDs must hold |
| `entitlementPackage` | MAY | Package-credential SAID used to compare a reader with a label |

1. `requiredPhases` SHOULD be `#ALL`. A pass of one phase is not evidence
   that a skeleton is valid; see Annex B.
2. A requester's choice of package or policy is advisory. The release
   agent MUST apply only release-policy credentials issued by its
   governance authority.

## 5 Labelled objects

1. Each [[ref: labelled part]] MUST be a private ACDC whose attributes
   contain the content and the part's own label as policy-namespace XML.
2. A [[ref: labelled object]] MUST:
   - reference each part by an edge with operator `NI2I`;
   - carry its [[ref: skeleton]] in [EXC-C14N] form as an
     attribute.
3. In the skeleton:
   - all markup in `policyNamespaces` MUST be kept verbatim, text
     included;
   - each host element's text MUST be replaced by the corresponding
     part's SAID.
4. Labelled objects and parts MUST be issued by a [[ref: labeller]] and
   anchored in that labeller's KEL.
5. A release agent MUST verify that:
   - the set of part SAIDs in the skeleton equals the set of edge `n`
     values, with no duplicates;
   - each part's label equals the corresponding skeleton markup.

   A part with no label MUST be withheld.

## 6 Oracle Trust Tasks

Type URIs take the form
`https://{authority}/spec/policy-oracle/{task}/0.1`, where `{authority}` is
a domain the publisher controls, until they are registered under
[TRUST-TASKS].

| Task | Request `payload` | Response `payload` |
|---|---|---|
| `discover` | `{ package }` | `{ phases, entryPoints }` |
| `evaluate` | `{ package, policy, document }` | `{ result, svrl, attestation }` |
| `transform` | `{ package, policy, document, entryPoint }` | `{ output, attestation }` |

1. `package` and `policy` are REQUIRED SAIDs. `document` is the compact
   labelled-object ACDC.
2. The oracle MUST:
   - evaluate exactly the named package and policy;
   - verify the document's SAID;
   - extract the skeleton itself.
3. An oracle MUST NOT accept a skeleton supplied separately from its
   labelled object.
4. `result` MUST be `noViolationsFound` or `violationsFound`.
5. `transform` MUST be refused unless a `noViolationsFound` evaluation of
   the same document under the same policy exists. Output matching an
   `errorPatterns` entry MUST be returned as an error.
6. Errors MUST be returned as `trust-task-error` responses with these
   codes:
   - `policy-oracle:unknownPackage`
   - `policy-oracle:unknownPolicy`
   - `policy-oracle:unknownPhase`
   - `policy-oracle:unknownEntryPoint`
   - `policy-oracle:packageIncomplete`
7. Request documents MUST carry `proof` until a Trust Tasks binding for
   [TSP] permits omitting it.

## 7 Execution requirements

1. The URI resolver MUST serve only files inside the verified tree. Any
   other request MUST raise an error. It MUST NOT return an empty
   document.
2. Input containing a document type declaration MUST be rejected.
3. The oracle MUST NOT set stylesheet parameters from request content.
4. Phase identifiers MUST match a declared phase exactly before they are
   substituted into `phaseXsl`. `#ALL` maps to `allXsl`.
5. `xsl:result-document` and engine extension functions MUST be
   disabled.
6. The oracle MUST enforce CPU, memory and input-size limits.
7. Inputs MUST be supplied without a system identifier. The engine's
   exact build and configuration, and its default language, MUST be fixed
   and recorded.
8. The oracle SHOULD keep compiled stylesheets resident.

## 8 Attestations

An [[ref: evaluation attestation]] MUST have:
- edges, with operator `NI2I`, to the package credential, the
  release-policy credential and the labelled object;
- attributes `phases`, `result`, `svrlSha256`, `xsdResult`, `engine` and
  `issuedAt`.

An [[ref: access-decision attestation]] MUST have:
- edges to the evaluation attestation, the labelled part, and each
  entitlement credential relied on;
- attributes `reader`, the TEL state and sequence number of each
  entitlement, `entitlementResult`, `issuedAt` and `expiresAt`.

Verification and use:

1. A verifier that recompiles the Schematron instead of using `allXsl` or
   `phaseXsl` MUST compare the set of failed assertions (rule identifier
   and location), not `svrlSha256`.
2. An access-decision attestation MUST NOT be used for any other reader
   or part, or after `expiresAt`.
3. A release agent MUST re-read entitlement TEL state at the moment of
   release.

## 9 Release exchange

1. A reader requests a part with IPEX `apply`.
2. Without a current evaluation attestation with `noViolationsFound` and a
   current access-decision attestation for that reader and part, the
   release agent MUST reply `spurn`.
3. Otherwise it proceeds `offer` → `agree` → `grant` → `admit`.
4. The `grant` MUST be carried in a confidential TSP payload to the
   reader's VID. In routed mode it MUST be end-to-end encrypted.
5. A `spurn` MUST NOT state a reason.
6. The release agent SHOULD notify the labelled object's owner of every
   `spurn`, naming the reader and the part.
7. If the required evaluation of the labelled object fails, every part of
   it MUST be withheld.
8. If no `entitlementPackage` is configured, the release agent MUST deny.

## 10 Security and privacy considerations

**Labels are content.** In many domains a label value reveals that a
program, a source or a relationship exists. The skeleton, attestations and
TEL events MUST be treated as sensitive at the level of the most sensitive
label they reference. The oracle, the release agent and the witnesses of
entitlement registries MUST operate inside the [[ref: deployment
boundary]].

**Linkage.** Part SAIDs are stable for life. Taken together, evaluation and
access-decision histories map who labelled what and who read what.
Attestations MUST NOT be published outside the deployment boundary. A
deployment MUST define a retention policy for them.

**Entitlement rosters.** A TEL of entitlement credentials is a roster of who
holds which access. Entitlement credentials SHOULD be private ACDCs, and
their registries' witnesses MUST be inside the deployment boundary.

**Honesty of labels.** Rules check consistency, not correctness. An
attestation of `noViolationsFound` MUST NOT be presented as certifying that
a label is correct. Label honesty rests on the labeller's signature and
authority.

**Producer-controlled scope.** A policy package may let markup inside the
document switch off rules or exclude parts from aggregation. A release
policy MUST use `assertions` to forbid such markup wherever the domain
requires those rules.

**Oracle shopping.** Only oracles listed in `trustedOracles` are honoured.

**Limits.** This specification protects labels and their binding to
content. It does not protect the people the content concerns.

## Annex A (informative): ISM profile

Example values for the US Intelligence Community Information Security
Marking package, V2022-NOV.

| Attribute | Value |
|---|---|
| `packageName`, `packageVersion` | `ISM`, `2021-NOVr2022-NOV` |
| `archiveSha256` | `0d6764205fe1a3158ba257a3143effe63f8129e22432d6405e117dc7f09fc7f2` (`ISM-Public-Convenience-2022-DEC-Public.zip`) |
| `schematron` | `Schematron/ISM/ISM_XML.sch` |
| `allXsl` | `Schematron/ISM/ISM_XML.xsl` |
| `phaseXsl` | `Schematron/ISM/ISM_XML-{phase}-phase.xsl` |
| `xsd` | `Schema/ISM/IC-ISM.xsd`, `IC-ARH.xsd`, `IC-NTK.xsd` |
| `policyNamespaces` | `urn:us:gov:ic:ism`, `urn:us:gov:ic:ntk`, `urn:us:gov:ic:arh` |
| `versionAttr`, `versionPattern` | `ism:DESVersion`, `^202111.202211(-.{1,23})?$` |
| `xsltVersion` | `2.0` |

The ISM release policy:

- **`failOn`:** `{attr: "role", values: ["error", "fatal"], unknown: "fail"}`.
- **`assertions`:**
  - `ism:compliesWith` contains `USGov`. That token gates 173 rule files.
  - No part element carries `ism:excludeFromRollup="true"`.
- **`createDateAttr`:** `ism:createDate`.

ISM V13 (2016) declares no phases. Its credential would omit `phaseXsl`.

## Annex B (informative): Test evidence

The tests ran on 2026-10-21 with Saxon-HE 12.5 on OpenJDK 21, using the ISM
V2022-NOV Convenience package.

- **ODNI examples:** all 52 run with 0 errors and 0 failed assertions.
- **Invalid inputs:** all 7 are caught (a banner lower than a portion, a
  missing owner, unknown classification, SCI and SAR values).
- **Skeletons:** those that follow clause 5 pass.
- **Single phases are not enough.** INFRASTRUCTURE, ROLLDOWN and TYPECHECK
  passed every invalid input, and BANNER passed an unknown SCI value.

The following were tested on a hand-assembled equivalent tree, not on the
Convenience package itself:

- **Determinism:** output is byte-identical across runs and directories.
- **Recompilation:** a SchXslt 1.10.1 recompile matched all 150 phase-input
  pairs on failed-assertion sets.
- **Sandbox:** a `file:`-only, no-network run gave identical output.

## Annex C (informative): Known limitations

- **XSLT 3.0** packages need an engine that supports it.
- **XSD validation** needs a validator beyond Saxon-HE.
- **Non-Schematron packages** are not covered by this version.
- **Entitlement comparison** through `entitlementPackage` is untested.
- **Accreditation** is out of scope.

## Bibliography

- ODNI, *XML Data Encoding Specification for Information Security Marking
  Metadata* (`DesIsmXml.pdf`, in the ISM package).
- NATO, STANAG 4774 (confidentiality metadata label syntax) and STANAG
  4778 (metadata binding).
- IETF RFC 2634, *Enhanced Security Services for S/MIME* (security labels).
- IETF RFC 5755, *An Internet Attribute Certificate Profile for
  Authorization* (clearance attribute).
- OpenTDF / Trusted Data Format, ODNI.
