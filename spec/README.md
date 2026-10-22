# ToIP specs

Local copies of Trust over IP specifications, joined from the `trustoverip`
GitHub repos into single Markdown files. Moved here from
`~/PROJECT/IETF/specs/` on 2026-10-21. The Spec-Up(-T) `specs.json` files are
joined in `markdown_paths` order. Where a repo has a `terms-definitions/`
directory, its term files are spliced, sorted by filename, after
`terms-and-definitions-intro.md`.

## Provenance

**Added 2026-10-20**: the Trust over IP (ToIP) TAS, TSP, TRQP, did:webs, CESR, KERI and
ACDC specs were added as joined Spec-Up Markdown.

**Refreshed 2026-10-21 (ToIP)**: checked every non-archived
`trustoverip` spec repo. 16 docs were added (DTGWG, AIMWG, governance,
glossaries, Dossier, did:x509, TR service profile). TSP was updated to
Release 1.0. The 2026-10-20 joins of did:webs, CESR, KERI and ACDC had
left out the Spec-Up-T `terms-definitions/` files. Those were rebuilt
with the term files spliced, sorted by filename, after
`terms-and-definitions-intro.md`, where Spec-Up-T renders them. TAS and
TRQP were unchanged upstream and have no term directory. Not fetched:
`aimwg-tsp-enabled-ai-agent-protocols` and `kswg-main-glossary` (empty
repos), `tswg-trust-registry-query-language` (template scaffolding, no
spec text), `dtgwg-trust-tasks-tf` `SPEC.md` (a generated copy of
`dtgwg-trust-tasks-spec`), and `tswg-did-method-webs-specification`
(superseded by the `kswg-` repo).

## Index

| Doc | Format / source | Spec status |
|---|---|---|
| `toip-tas.md` | Spec-Up Markdown, `trustoverip/TechArch` main @ `73397d7` (`spec/spec.md`, 1 file in `specs.json`) | ToIP Technology Architecture Specification, Public Review Draft 02 (02 September 2024) |
| `toip-tsp.md` | Spec-Up Markdown, `trustoverip/tswg-tsp-specification` main @ `ccda6b3` (`spec/spec.md`, 1 file in `specs.json`) | Trust Spanning Protocol (TSP) Specification, Release 1.0 |
| `toip-trqp.md` | Spec-Up Markdown, `trustoverip/tswg-trust-registry-protocol` main @ `6863733` (`specification/v2-approved/`, 10 files joined in `specs.json` order) | ToIP Trust Registry Query Protocol (TRQP) v2.0, ToIP Approved Deliverable |
| `toip-trust-registry-service-profile.md` | Markdown source, `trustoverip/tswg-trust-registry-service-profile` main @ `4ea281b` (`spec.md`) | ToIP Service Profile Specification, Pre-Draft 0.0.1 |
| `toip-did-webs.md` | Spec-Up-T Markdown, `trustoverip/kswg-did-method-webs-specification` main @ `2d84ef2` (`spec/`, 3 files in `specs.json` order + 38 term files) | ToIP did:webs Method Specification v0.10.3 |
| `toip-did-x509.md` | Spec-Up Markdown, `trustoverip/tswg-did-x509-method-specification` main @ `fffc867` (`spec/`, 13 files joined in `specs.json` order) | did:x509 Method Specification v1.0 Draft |
| `toip-cesr.md` | Spec-Up-T Markdown, `trustoverip/kswg-cesr-specification` main @ `bad6edd` (`spec/`, 3 files in `specs.json` order + 25 term files) | Composable Event Streaming Representation (CESR) v1.1 |
| `toip-keri.md` | Spec-Up-T Markdown, `trustoverip/kswg-keri-specification` main @ `fbdd4a6` (`spec/`, 3 files in `specs.json` order + 56 term files) | Key Event Receipt Infrastructure (KERI) v1.1 |
| `toip-acdc.md` | Spec-Up-T Markdown, `trustoverip/kswg-acdc-specification` main @ `f0bd097` (`spec/`, 3 files in `specs.json` order + 39 term files) | Authentic Chained Data Containers (ACDC) v1.1 |
| `toip-dossier.md` | Spec-Up-T Markdown, `trustoverip/kswg-dossier-specification` main @ `6fcf841` (`spec/`, 3 files in `specs.json` order + 29 term files) | Verifiable Dossiers v0.7 Draft |
| `toip-tmcp.md` | Spec-Up Markdown, `trustoverip/aimwg-tmcp-specification` main @ `9ed9e62` (`spec/`, 11 files joined in `specs.json` order) | TMCP: MCP over TSP Specification v0.1 Draft |
| `toip-dtg-vti.md` | Spec-Up-T Markdown, `trustoverip/dtgwg-vti-spec` main @ `7ce6f65` (`spec/`, `specs.json` order + 37 term files) | Verifiable Trust Infrastructure (VTI) Specification, Working Draft 0.2.0 |
| `toip-dtg-cred.md` | Spec-Up-T Markdown, `trustoverip/dtgwg-cred-spec` main @ `2e3c5be` (`spec/`, 5 files in `specs.json` order + 50 term files) | DTG Credentials Core Specification, Working Draft 0.6.0 |
| `toip-dtg-vsc-registry.md` | Joined Markdown, `trustoverip/dtgwg-vsc-registry` main @ `7b30c75` (`README.md`, `GOVERNANCE.md`, each `predicates/<name>/<n>/profile.md` + `predicate.jsonld`) | DTG VSC Predicate Registry; all predicates `draft` |
| `toip-dtg-zkp.md` | Spec-Up-T Markdown, `trustoverip/dtgwg-zkp-spec` main @ `aa4e285` (`spec/`, 10 files in `specs.json` order + 27 term files) | Decentralized Trust Graph — Zero-Knowledge Proof Specification, Working Draft 0.1.0 |
| `toip-dtg-trust-tasks.md` | Spec-Up-T Markdown, `trustoverip/dtgwg-trust-tasks-spec` main @ `9449932` (`spec/`, 5 files in `specs.json` order + 20 term files) | Trust Tasks, Working Draft 0.7.0 |
| `toip-dtg-vds.md` | Spec-Up-T Markdown, `trustoverip/dtgwg-vds-spec` main @ `f8cdcb3` (`spec/`, 5 files in `specs.json` order + 2 term files) | DTG Verifiable Data Structures; unfilled template stub |
| `toip-dtg-agent-names.md` | Spec-Up-T Markdown, `trustoverip/dtgwg-agent-names-spec` main @ `fed492c` (`spec/`, 5 files in `specs.json` order + 2 term files) | DTG Agent Names; unfilled template stub |
| `toip-governance-metamodel.md` | Spec-Up-T Markdown, `trustoverip/egwg-governance-metamodel` main @ `0f2f6e7` (`spec/`, 4 files in `specs.json` order + 10 term files) | Governance Framework Metamodel |
| `toip-main-glossary.md` | Spec-Up-T Markdown, `trustoverip/ctwg-main-glossary` main @ `00608bb` (`spec/`, 11 files in `specs.json` order + 543 term files) | ToIP Main Glossary v1.0, Public Review Draft 01 |
| `toip-general-glossary.md` | Spec-Up-T Markdown, `trustoverip/ctwg-general-glossary` main @ `73604cf` (`spec/`, 5 files in `specs.json` order + 215 term files) | CTWG General Glossary, Public Review Draft 01 |
| `toip-kerisuite-glossary.md` | Spec-Up-T Markdown, `trustoverip/kerisuite-glossary` main @ `0da7b2c` (`spec/`, 5 files in `specs.json` order + 336 term files) | KERI Suite Glossary, Public Review Draft 01 |
| `toip-terminology-governance-guide.md` | Spec-Up-T Markdown, `trustoverip/ctwg-terminology-governance-guide` main @ `77fdb38` (`spec/`, `specs.json` order + 11 term files) | ToIP Terminology Governance Guide v1.0.8 draft |

## ODNI ISM (`ism/ISM/`)

IC Information Security Marking (ISM) public standalone package, version
`2021-NOVr2022-NOV` (ISM V2022-NOV), build 228, built 2023-06-09
(`ism/ISM/ISMpackage.properties`). Extracted unmodified from
`ISM-Public-Standalone.zip`.

- Upstream URL: `https://www.dni.gov/files/documents/CIO/ICEA/Dec2022/ISM/ISM-Public-Standalone.zip`.
  ODNI returns HTTP 403 to non-browser clients, so the zip was fetched on
  2026-10-21 from the Wayback Machine capture
  `https://web.archive.org/web/20260522215644id_/` of that URL.
- Zip SHA-256 `29362fedb43f85b2d453977d76151bfec81875c9fbb60cd46867eb30004eea81`,
  10967574 bytes. Its SHA-1 matches the Wayback CDX digest
  `NWYQXCZ3SMPVW7H2743RMXSJF5PLBG3Q`. That digest is identical across 9
  captures on `www.dni.gov` and `www.odni.gov` from 2025-02-21 to
  2026-05-22.
- The zip extracts to 1221 files. Every well-formed entry in ODNI's
  `ism/ISM/manifest.md5` passes `md5sum -c`: 1219 entries, with 2 lines
  malformed.
- The XSL and Schematron are XSLT 2.0 (`queryBinding="xslt2"`). They need
  Saxon or equivalent, not libxslt.
- Public-release gaps: every CVE value is `(U)`, and the CVEs carry a
  per-value `ValueClassification` column. `CVEnumISMSAR` (SAR programs) is
  empty. Unclassified SCI control systems (HCS, SI, TK, KLM, ...) are
  present.
