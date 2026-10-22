KERI Suite Glossary
==================

**Specification Status**: Public Review Draft 01 (PR1)

**Latest Draft:**

* [Github Repository](https://github.com/trustoverip/kerisuite-glossary)
* [Submit/View Issues](https://github.com/trustoverip/kerisuite-glossary/issues)
* [Discussions](https://github.com/trustoverip/kerisuite-glossary/discussions)

**Editors:**

* [Samuel Smith](https://github.com/SmithSamuelM), [Prosapien](https://www.prosapien.com)
* [Drummond Reed](https://github.com/talltree), [Gen](https://www.gendigital.com)
* [Henk van Cann](https://github.com/henkvancann), [Blockchainbird](https://www.blockchainbird.com)

**Contributors:**
* [Kor Dwarshuis](https://github.com/kordwarshuis/), [Blockchainbird](https://www.blockchainbird.com)

**Contributors:**

**Participate:**

* [GitHub repo](https://github.com/weboftrust/kerisuite-glossary)
* [Commit history](https://github.com/weboftrust/kerisuite-glossary/commits/main)

------------------------------------

## Status

This is the first public review draft of the KERI Main Glossary. It is also the first version published using the [Spec-Up-T specification editing utility](https://github.com/trustoverip/spec-up-t)
based on [Spec-Up specification editing utility](https://identity.foundation/spec-up/) developed by the [Decentralized Identity Foundation](http://identity.foundation/).

## Copyright Notice

This specification is subject to the **OWF Contributor License Agreement 1.0 - Copyright**
available at
[https://www.openwebfoundation.org/the-agreements/the-owf-1-0-agreements-granted-claims/owf-contributor-license-agreement-1-0-copyright](https://www.openwebfoundation.org/the-agreements/the-owf-1-0-agreements-granted-claims/owf-contributor-license-agreement-1-0-copyright).

These terms are inherited from the [KERI Suite Working Group](https://wiki.trustoverip.org/display/HOME/Keri+Suite+Working+Group) at the Trust over IP (ToIP) Foundation. [Working Group Charter](https://trustoverip.org/wp-content/uploads/TSWG-2-Charter-Revision.pdf)


## Terms of Use

These materials are made available under and are subject to the [OWF CLA 1.0 - Copyright & Patent license](https://www.openwebfoundation.org/the-agreements/the-owf-1-0-agreements-granted-claims/owf-contributor-license-agreement-1-0-copyright-and-patent). Any source code is made available under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0.txt).

THESE MATERIALS ARE PROVIDED “AS IS.” The Trust Over IP Foundation, established as the Joint Development Foundation Projects, LLC, Trust Over IP Foundation Series ("ToIP"), and its members and contributors (each of ToIP, its members and contributors, a "ToIP Party") expressly disclaim any warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to the materials. The entire risk as to implementing or otherwise using the materials is assumed by the implementer and user.

IN NO EVENT WILL ANY ToIP PARTY BE LIABLE TO ANY OTHER PARTY FOR LOST PROFITS OR ANY FORM OF INDIRECT, SPECIAL, INCIDENTAL, OR CONSEQUENTIAL DAMAGES OF ANY CHARACTER FROM ANY CAUSES OF ACTION OF ANY KIND WITH RESPECT TO THESE MATERIALS, ANY DELIVERABLE OR THE ToIP GOVERNING AGREEMENT, WHETHER BASED ON BREACH OF CONTRACT, TORT (INCLUDING NEGLIGENCE), OR OTHERWISE, AND WHETHER OR NOT THE OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

## Introduction

The KERI Main Glossary is a deliverable of the ToIP KERI Suite Working Group (KSWG). Its purpose is to promote shared understanding of terms and concepts across the many different working groups, communities, enterprises, and ecosystems who are collaborating to develop and deploy decentralized digital trust infrastructure.

Contributions and feedback are encouraged from any stakeholder in this area of terminology.

## Linking to this Glossary

This glossary is designed to be both human and machine readable. All terms are listed alphabetically; acronyms are listed separately and linked to the fully expanded terms. Document authors can link directly to any term using standard web links and anchors following this syntax:

  `https://trustoverip.github.io/kerisuite-glossary#term:xxxxx`

Where `xxxxx` is the term as it appears in the glossary, with any spaces are replaced by en-dashes (hyphens). For example, a link to the term `self-certifying identifer` would be:

  `https://trustoverip.github.io/kerisuite-glossary#self-certifiying-identifier`

A specification document written using the [Trustoverip](https://trustoverip.org)'s open source [Spec-Up-T environment](https://trustoverip.github.io/spec-up-t/) documented in the [Spec-Up-T manual](https://trustoverip.github.io/spec-up-t-website/), originally based on [Decentralized Identity Foundation](http://identity.foundation/)'s open source [Spec-Up editor](https://identity.foundation/spec-up/).

The tool may create special external references to terms in this glossary using the Spec-Up `xref` and the `tref` tags following this syntax:

  `[ [xref: glossary, xxxxx] ]` and   `[ [tref: glossary, xxxxx] ]`
  
Note: we've put spaces between brackets to be able to present this literally; remove the spaces in use. 

  Where `glossary` is the text label the document author assigns to the URL of a Web-accessible glossary, and `xxxxx` is the term as it appears in that glossary, with any spaces are replaced by en-dashes (hyphens). For example, a Spec-Up external reference to the term `self-certifying identifer` using the label `toip` for this glossary would look like this:

  `[[xref: toip1, self-certifying-identifier]]`

An item borrowed from an other glossary might look like this:

  `[[xref: toip2, hash]]`

An alias is used to the generate the preferred spelling on the receiving end:
`[ [tref: glossary, xxx-xx, Xxx Xx] ]`

leads to 'Xxx Xx' as the term in the glossary that's collected via the key 'xxx-xx'
## Referenced Glossaries

These glossaries have been interlinked using `tref` and `xref` tags. We show both test and production environments. The `specs.json` is for proficient users to inspect the production settings.

### Interlinked glossary summary
|Glossary| TEST repo | Live TEST Glossary | Production repo  | Live PRODUCTION Glossary | Specs.json PROD |
| :---- | :-- | :-- |:-- |:-- |:-- |
|KERIsuite|[HenkvanCann](https://github.com/henkvancann/kerisuite-glossary)|[TEST](https://henkvancann.github.io/kerisuite-glossary/)|[WebofTrust](https://github.com/weboftrust/kerisuite-glossary)|[PRODUCTION](https://weboftrust.github.io/kerisuite-glossary/)|[Specs.json](https://github.com/weboftrust/kerisuite-glossary/blob/main/specs.json)|
|vLEI|[HenkvanCann](https://github.com/henkvancann/vlei-glossary)|[TEST](https://henkvancann.github.io/vlei-glossary/)|||[Specs.json](https://github.com/henkvancann/vlei-glossary/blob/main/specs.json)|
|ToIP **Main**|[HenkvanCann](https://github.com/henkvancann/ctwg-main-glossary)|[TEST](https://henkvancann.github.io/ctwg-main-glossary/)|[ToIP](https://github.com/trustoverip/ctwg-main-glossary)|[PRODUCTION](https://trustoverip.github.io/ctwg-main-glossary/)|[Specs.json](https://github.com/trustoverip/ctwg-main-glossary/blob/main/specs.json)|
|ToIP **General IT**|[HenkvanCann](https://github.com/henkvancann/ctwg-general-glossary)|[TEST](https://henkvancann.github.io/ctwg-general-glossary/)|[ToIP](https://github.com/trustoverip/ctwg-general-glossary)|[PRODUCTION](https://trustoverip.github.io/ctwg-general-glossary/)|[Specs.json](https://github.com/trustoverip/ctwg-general-glossary/blob/main/specs.json)|


The following glossaries were used as sources for some of the definitions in the ToIP General Glossary. All source glossaries are cited in the definitions of each term.

| Short Name | Source Glossary | URL |
|------------|-----------------|-----|
| Wikipedia | Wikipedia | [https://www.wikipedia.org/](https://en.wikipedia.org/wiki/Main_Page) |
| eSSIF-Lab | eSSIF-Lab Glossary | https://essif-lab.github.io/framework/docs/essifLab-glossary |
| NIST-CSRC | NIST Computer Security Resource Center Glossary | https://csrc.nist.gov/glossary/ |
| W3C DID | W3C Decentralized Identifiers (DIDs) 1.0 | https://www.w3.org/TR/did-core/#terminology |
| W3C VC | W3C VC Data Model 1.1 | https://www.w3.org/TR/vc-data-model/#terminology |


## Terms and Definitions

<!-- Leave this code snippet if you want an alphabet index -->
<div id="alphabet-index-h7vc6omi2hr2880"></div>

- - -
<!-- End of code snippet for alphabet index -->
[[def: abandoned-identifier, Abandoned identifier]]

~ An [[ref: AID]] is abandoned when either the [[ref: inception-event]] or a subsequent [[ref: rotation-event]] rotates to an empty next key digest list (which means the next threshold must also be 0).

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/abandoned-identifier">extended KERI glossary</a>

[[def: access-controlled-interaction, Access-controlled interaction]]

~ Access controlled actions like submitting a report. If you already have that report then load balancer needs a mechanism to drop repeated requests.

~ Source: Samuel Smith / Daniel Hardman / Lance Byrd - Zoom meeting KERI Suite Jan 16 2024; discussion minute 30-60 min

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/access-controlled-interaction">extended KERI glossary</a>

[[def: ACDC]]

~ [[ref: authentic-chained-data-container]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ACDC">extended KERI glossary</a>

[[def: ADC]]

~ [[ref: authentic-data-container]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ADC">extended KERI glossary</a>

[[tref:toip1, agency]]

[[tref: toip1, agent]]

[[def: AID]]

~ [[ref: autonomic-identifier]]

~ ToIP specific : [[xref: toip1, autonomic-identifier, Autonomic identifier]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/AID">extended KERI glossary</a>

[[def: ambient-verifiability, Ambient verifiability]]

~ Verifiable by anyone, anywhere, at anytime. Although this seems a general term, it was first used in the context of KERI by Sam Smith.

~ _Ambient Duplicity Detection_ is an example of ambient verifiability that describes the possibility of detecting duplicity by anyone, anywhere, anytime.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ambient-verifiability">extended KERI glossary</a>

[[def: ample]]

~ The minimum required number of participants in an event to have a [[ref: supermajority]] so that one and only one agreement or consensus on an event may be reached. This is a critical part of the [[ref: KAACE]] agreement algorithm (consensus) in KERI for establishing consensus between witnesses on the key state of a KERI identifier. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ample">extended KERI glossary</a>

[[def: APC]]

~ [[ref: authentic-provenance-chain]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/APC">extended KERI glossary</a>

[[def: Attribute]]

~ a top-level field map within an ACDC that provides a property of an entity that is inherent or assigned to the entity.

~ Also see: [[xref: toip1, attribute]]

[[tref: toip1, attributional-trust]]

[[def: authentic-chained-data-container, authentic-chained data container, ACDC]]

~ a directed acyclic graph with properties to provide a verifiable chain of [[ref: proof-of-authorship]]. See the full [specification](https://trustoverip.github.io/kswg-acdc-specification/)  
~ Source: Dr. S.Smith, 2024

~ Explained briefly, an ACDC or [[ref: authentic-data-container]] proves digital data consistency and authenticity in one go. An ACDC cryptographically secures commitment to the data contained, and its identifiers are self-addressing, which means they point to themselves and are also contained in the data.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/authentic-chained-data-container">extended KERI glossary</a>

[[def: authentic-data-container, authentic-data container, ADC]]

~ A mechanism for conveying data that allows the [[ref: authenticity]] of its content to be proved.

~ **Instance**  
~ A [Verifiable Credential](https://w3.org/TR/vc-data-model/) is an [[ref: authentic-chained-data-container]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/authentic-data-container">extended KERI glossary</a>

[[def: authentic-provenance-chain, Authentic provenance chain]]

~ Interlinked [[ref: presentation-exchange]] of evidence that allow data to be tracked back to its origin in an objectively [[ref: verifiable]] way.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/authentic-provenance-chain">extended KERI glossary</a>

[[def: authentic]]

~ ~The origin and content of any statement by a party to a conversation are provable to any other party.

~ Also see [[ref: authenticity]]

[[def: authenticity]]

~ ~Authenticity is primarily about control over the key state needed to prove who said what in the conversation via digital
~ signatures. In other words, it is about secure attribution.

~ Also see [[ref: authentic]]

[[def: authoritative, Authoritative]]

~ Established control [[ref: authority]] over an identifier, that has received attestations to it, e.g. control over the identifier has been verified to its root-of-trust. So the (control over the) identifier is 'authoritative' because it can be considered accurate, renowned, honourable and / or respected.    
~ Also used to describe [[ref: PKI]] key pairs that have this feature.

~ In TrustoverIP context: [[xref:toip1, authoritative]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/authoritative">extended KERI glossary</a>

[[def: autonomic-identifier, Autonomic identifier, Autonomic identifiers, AID]]

~ a self-managing cryptonymous identifier that must be self-certifying (self-authenticating) and must be encoded in CESR as a qualified Cryptographic primitive.  
~ Source: Dr. S.Smith, 2024

~ An identifier that is [[ref: self-certifying-identifier]] and [[ref: self-sovereign-identity]] (or *self-managing*).

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/autonomic-identifier">extended KERI glossary</a>

[[def: autonomic-trust-basis, Autonomic trust basis]]

~ When we use an [[ref: AID]] as the [[ref: root-of-trust]] we form a so-called *autonomic trust basis*. This is diagrammed as follows:

~ ![](https://github.com/WebOfTrust/WOT-terms/blob/0582b911fee7cdf0e2730df788bb5afd38d31e14/static/img/autonomic-trust-basis.png?raw=true) 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/autonomic-trust-basis">extended KERI glossary</a>

[[def: backer, Backer]]

~ an alternative to a traditional KERI based [Witness](https://trustoverip.github.io/kswg-keri-specification/#term:witness) commonly using Distributed Ledger Technology (DLT) to store the [KEL](https://trustoverip.github.io/kswg-keri-specification/#term:kel) for an identifier.   
~ Source: Dr. S.Smith, 2024

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/backer">extended KERI glossary</a>

[[def: BADA]]

~ [[ref: best-available-data-acceptance-mechanism]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/BADA">extended KERI glossary</a>

[[def: base-media-type, Base media type]]

~ `credential` plus `ld` plus `json`.

~ Other media types of credentials are allowed by must provide either unidirectional or bidirectional transformations.  So, for example, we would create credential+acdc+json and provide a unidirectional transformation to credential+ld+json.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/base-media-type">extended KERI glossary</a>

[[def: bespoke-credential, Bespoke credential]]

~ It's an [[ref: issuance-event]] of the disclosure or presentation of other ACDCs. _Bespoke_ means _Custom_ or _tailor made_.
~ A bespoke credential serves as an on-the-fly contract with the issuee; it's a self-referencing and self-contained contract between the issuer and the verifier. Mind you, here the issuer and issuee are merely the discloser and disclosee of another (set of) ACDC(s).

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/bespoke-credential">extended KERI glossary</a>

[[def: best-available-data-acceptance-mechanism, Best available data-acceptance mechanism, BADA]]

~ The BADA security model provides a degree of [[ref: replay-attack]] protection. The attributate originator (issuer, author, source) is provided by an attached signature couple or quadruple. A single reply could have multiple originators. When used as an [[ref: authorization]] the reply attributes may include the identifier of the authorizer and the logic for processing the associated route may require a matching attachment.
~ BADA is part of [[ref: KERI]]'s [Zero Trust Computing Architecture for Data Management](https://hackmd.io/Qsrfj7Y-TIGl5ESvrxWGxw): How to support Secure Async Data Flow Routing in KERI enabled Applications.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/best-available-data-acceptance-mechanism">extended KERI glossary</a>

[[def: bexter, Bexter]]

~ The class variable length text that is used in CESR and preserves the round-trip transposability using Base64 URL safe-only encoding even though the text variable length.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/bexter">extended KERI glossary</a>

[[def: bis]]

~ bis = backed vc issue, registry-backed transaction event log credential issuance

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/bis">extended KERI glossary</a>

[[def: bivalent, Bivalent]]

~ A nested set of layered delegations in a [[ref: delegation]] tree, wraps each layer with compromise recovery protection of the next higher layer. This maintains the security of the root layer for compromise recovery all the way out to the leaves in spite of the leaves using less secure key management methods.  

~ ![bivalent-key-management-infrastructure](https://github.com/WebOfTrust/WOT-terms/blob/0582b911fee7cdf0e2730df788bb5afd38d31e14/static/img/bivalent-delegated-key-management-infrastructure.png?raw=true)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/bivalent">extended KERI glossary</a>

[[def: blind-oobi, Blind OOBI]]

~ A blind [[ref: OOBI]] means that you have some mechanisms in place for verifying the [[ref: AID]] instead of via the OOBI itself. A blind OOBI is essentially a [[ref: URL]]. It's called "blind" because the witness is not in the OOBI itself. You haves other ways of verifying the AID supplied. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/blind-oobi">extended KERI glossary</a>

[[def: blinded-revocation-registry, Blinded revocation registry]]

~ The current state of a [[ref: transaction-event-log]] (TEL) **may be hidden or blinded** such that _the only way_ for a potential verifier of the state to observe that state is _when the controller of a designated AID discloses it_ at the time of presentation.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/blinded-revocation-registry">extended KERI glossary</a>

[[def: bran]]

~ A cryptographic string used as a primary input, a seed, for creating key material for and [[ref: autonomic-identifier]]. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/bran">extended KERI glossary</a>

[[def: brv]]

~ brv = backed vc revoke, registry-backed transaction event log credential revocation

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/brv">extended KERI glossary</a>

[[def: cesr-proof-signatures, CESR proof signatures]]

~ CESR Proof Signatures is an extension to the Composable Event Streaming Representation [CESR] that provides transposable cryptographic signature attachments on self-addressing data [[ref: SAD]]. Any SAD, such as an Authentic Chained Data Container (ACDC) Verifiable Credential [ACDC], for example, may be signed with a CESR Proof Signature and streamed along with any other CESR content. In addition, a signed SAD can be embedded inside another SAD, and the CESR proof signature attachment can be transposed across envelope boundaries and streamed without losing any cryptographic integrity.
~ Source: (Philip Feairheller, IETF-cesr-proof)

~ <img src="https://hackmd.io/_uploads/ByxcPBQT5.png" width="600" height="350"/>
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/cesr-proof-signatures">extended KERI glossary</a>

[[def: CESR-version, CESR version]]

~ the CESR Version is provided by a special Count Code that specifies the Version of all the CESR code tables in a given Stream or Stream section.
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/CESR-version">extended KERI glossary</a>

[[def: CESR]]

~ [[ref: composable-event-streaming-representation]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/CESR">extended KERI glossary</a>

[[def: cesride, Cesride]]

~ is concerned with parsing CESR primitives.

~ Cesride is built from cryptographic primitives that are named clearly and concisely. There are:
~ * [[ref: diger]]
~ * [[ref: verfer]]
~ * [[ref: signer]] 
~ * [[ref: siger]]
~ * [[ref: cigar]]
~ * [[ref: salter]]

~ Each primitive will have methods attached to it that permit one to generate and parse the qualified base2 or [[ref: base64]] representation. 
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/cesride">extended KERI glossary</a>

[[def: chain-link-confidential-disclosure, Chain-link confidential disclosure]]

~ contractual restrictions and liability imposed on a recipient of a disclosed [[ref: ACDC]] that contractually link the obligations to protect the disclosure of the information contained within the ACDC to all subsequent recipients as the information moves downstream. The Chain-link Confidential Disclosure provides a mechanism for protecting against un-permissioned exploitation of the data disclosed via an ACDC.

~ Source: Dr. S.Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/chain-link-confidential-disclosure">extended KERI glossary</a>

[[def: chain-link-confidentiality, Chain link confidentiality, CLC]]

~ Chains together a sequence of [[ref: disclosee]] which may also include a set of constraints on data usage by both second and third parties expressed in legal language such that the constraints apply to all recipients of the disclosed data thus the phrase "chain link" confidentiality. Each Disclosee in the sequence in turn is the [[ref: discloser]] to the next Disclosee.

~ This is the primary mechanism of granting digital data rights through binding information exchange to confidentiality laws. Confidentiality is dynamically negotiated on a per-event, per-data exchange basis according to the data that is being shared in a given exchange.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/chain-link-confidentiality">extended KERI glossary</a>

[[def: cigar]]

~ An **_un_**[[ref: indexed-signature]].   
~ [Source](https://github.com/WebOfTrust/cesride#terminology) by Jason Colburne
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/cigar">extended KERI glossary</a>

[[def: CLC]]

~ [[ref: chain-link-confidentiality]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/CLC">extended KERI glossary</a>

[[def: code-table-selector, Code table selector]]

~ the first character in the text code of [[ref: composable-event-streaming-representation]] that determines which [[ref: code-table]] to use, either a default code table or a code table selector character when not the default code table. Thus the 1 character text code table must do double duty. It must provide selectors for the different text code tables and also provide type codes for the most popular primitives that have a pad size of 1 that appear is the default code table.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/code-table-selector">extended KERI glossary</a>

[[def: cold-start-stream-parsing, Cold start stream parsing]]

~ After a reboot (or cold start), a stream processor looks for framing information to know how to parse groups of elements in the stream. 

~ If that framing information is ambiguous then the parser may become confused and require yet another cold start. While processing a given stream a parser may become confused especially if a portion of the stream is malformed in some way. This usually requires flushing the stream and forcing a cold start to resynchronize the parser to subsequent stream elements. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/cold-start-stream-parsing">extended KERI glossary</a>

[[def: compact-disclosure, Compact disclosure]]

~ a disclosure of an ACDC that discloses only the SAID(s) of some or all of its field maps. Both Partial and Selective Disclosure rely on Compact Disclosure.
  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/compact-disclosure">extended KERI glossary</a>

[[def: compact-variant, Compact variant]]

~ Either a [[ref: most-compact]] version of an ACDC or the [[ref: fully-compact]] version of an ACDC. An [[ref: issuer]] commitment via a signature to any variant of ACDC (compact, full, etc) makes a cryptographic commitment to the top-level section fields shared by all variants of that ACDC because the value of a [[ref: top-level-section]] is either the [[ref: SAD]] or the [[ref: SAID]] of the SAD of the associated section.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/compact-variant">extended KERI glossary</a>

[[def: composability, Composability]]

~ short for text-binary concatenation composability. An encoding has Composability when any set of Self-Framing concatenated Primitives expressed in either the Text domain or Binary domain may be converted as a group to the other Domain and back again without loss.  
~ Source: Dr. S.Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/composability">extended KERI glossary</a>

[[def: composable-event-streaming-representation, composable event streaming representation, CESR]]

~ Also called 'CESR'. This compact encoding scheme fully supports both textual and binary streaming applications of attached crypto material of all types. This approach includes [[ref: composability]] in both the textual and binary streaming domains. The [[ref: primitive]] may be the minimum possible but still composable size. 

~ Making composability a guaranteed property allows future extensible support of new compositions of streaming formats based on pre-existing core primitives and compositions of core primitives. This enables optimized stream processing in both the binary and text domains.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/composable-event-streaming-representation">extended KERI glossary</a>

[[def: composable, Composable]]

~ [[ref: composability]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/composable">extended KERI glossary</a>

[[def: confidential]]

~ ˜All statements in a conversation are only known by the parties to that conversation.

~ Also see: [[ref: confidentiality]]

[[def:  confidentiality]]

~ Confidentiality is primarily about control over the disclosure of what (content data) was said in the conversation and to
~ whom it was said (partitioning). Confidentiality is about control over the key state needed to hide content via encryption
~ vis-à-vis the intended parties.

~ Also see: [[ref: confidential]]

[[def: configuration-traits, Configuration traits]]

~ a list of specially defined strings representing a configuration of a KEL. 
~ Source: Dr. S.Smith, 2024
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/configuration-traits">extended KERI glossary</a>

[[tref: toip1, contextual-linkability]]

[[def: contingent-disclosure, Contingent disclosure]]

~ Contingent disclosure is a privacy-preserving mechanism where only specific information or attributes are disclosed under defined conditions. It enables the selective sharing of data such that only the required information is revealed to a relying party, without exposing other unrelated or sensitive details. [[ref: chain-link-confidentiality]] is a form of contingent disclosure.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/contingent-disclosure">extended KERI glossary</a>

[[def: contractually-protected-disclosure, Contractually-protected disclosure]]

~ a discloser of an ACDC that leverages a Graduated Disclosure so that contractual protections can be put into place to minimize the leakage of information that can be correlated. A Contractually Protected Disclosure partially or selectively reveals the information contained within the ACDC in the initial interaction with the recipient and discloses further information only after the recipient agrees to the terms established by the discloser. More information may be progressively revealed as the recipient agrees to additional terms.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/contractually-protected-disclosure">extended KERI glossary</a>

[[tref: toip1, control-authority, Control authority]]

[[def: controller-application, Controller application]]

~ Each [[ref: controller]] has an application or suite or applications called the controller application. 

~ The controller application provides five functions with respect to the digital signing key pairs that control the controller’s AID. These five functions manage the associated key state via key events. 

~ More: These functions are
~ * [[xref: toip2, key-pair, key pair]] generation,
~ * key pair storage,
~ * [[ref: key event]] generation,
~ * key event signing, and
~ * key event validation.

[[def: controller, Controller]]

~ an entity that can cryptographically prove the control authority over an AID and make changes on the associated KEL. A controller of a multi-sig AID may consist of multiple controlling entities.  
~ Source: Dr. S.Smith, 2024

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/controller">extended KERI glossary</a>

[[def: cooperative-delegation, Cooperative delegation]]

~ The way KERI addresses the [[ref: security-cost-performance-architecture-trade-off]] is via [[ref: delegation]] of identifier prefixes. Delegation includes a delegator and a delegate. For this reason we may call this a cooperative delegation. This is a somewhat **novel form of delegation**. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/cooperative-delegation">extended KERI glossary</a>

[[def: correlation, Correlation]]

~ In our scope this is an identifier used to indicate that external parties have observed how wallet contents are related. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/correlation">extended KERI glossary</a>

[[def: count-code, Count code]]

~ [[ref: group-framing-code]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/count-code">extended KERI glossary</a>

[[def: credential, Credential]]

~ Evidence of authority, status, rights, entitlement to privileges, or the like.  
~ ([source](https://github.com/trustoverip/tswg-acdc-specification/blob/main/draft-ssmith-acdc.md#introduction))   
~ A credential has its current state and a history, which is captured in a doc or a graph.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/credential">extended KERI glossary</a>

[[def: current-threshold, Current threshold]]

~ represents the number or fractional weights of signatures from the given set of current keys required to be attached to a [Message](https://trustoverip.github.io/kswg-keri-specification/#term:message) for the [Message](https://trustoverip.github.io/kswg-keri-specification/#term:message) to be considered fully signed.  
~ Source: Dr. S.Smith, 2024

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/current-threshold">extended KERI glossary</a>

[[def: custodial-agent, Custodial agent]]

~ An [[ref: agent]] owned by an individual who has granted [[ref: signing-authority]] to a custodian who is usually also the host of the running agent software. Using [[ref: partial-rotation]] to facilitate custodial key management the owner of the identifier retains [[ref: rotation-authority]] and thus the ability to "fire" the custodian at any time without requiring the cooperation of the custodian.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/custodial-agent">extended KERI glossary</a>

[[def: custodial-rotation, Custodial rotation]]

~ Rotation is based on control authority that is split between two key sets. The first for signing authority and the second (pre-rotated) for rotation authority, the associated thresholds and key list can be structured so that a designated custodial agent can hold signing authority, while the original controller can hold exclusive rotation authority.  
~ [[ref: partial-rotation]] supports the vital use case of custodial key rotation to authorize a [[ref: custodial-agent]].  
~ Paraphrased by @henkvancann based on the [IETF-KERI draft 2022](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md) by Samual Smith.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/custodial-rotation">extended KERI glossary</a>

[[def: dead-attack, Dead attack]]

~ an attack on an [[ref: establishment-event]] that occurs after the Key-state for that event has become stale because a later establishment event has rotated the sets of signing and pre-rotated keys to new sets. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/dead-attack">extended KERI glossary</a>

[[def: decentralized-identity, Decentralized identity]]

~ `KERI`s definition of decentralization (centralization) is about _control_ not _spatial distribution_. In our definition _decentralized_ is not necessarily the same as _distributed_. By distributed we mean that activity happens at more than one site. Thus decentralization is about _control_ and distribution is about _place_. To elaborate, when we refer to decentralized infrastructure we mean infrastructure under decentralized (centralized) control no matter its spatial distribution. Thus _decentralized infrastructure_ is infrastructure sourced or controlled by more than one `entity`.

~ TrustoverIP related [[xref: toip1, decentralized-identity, Decentralized identity]]

~ General IT description [[xref: toip2, decentralized-identity, Decentralized identity]]

[[def: delegated-identifier, Delegated identifier]]

~ Matches the act of [[ref: delegation]] with the appropriate digital twin. Consequently when applied recursively, delegation may be used to compose arbitrarily complex trees of hierarchical (delegative) key management event streams. This is a most powerful capability that may provide an essential building block for a generic universal decentralized key management infrastructure ([[ref: DKMI]]) that is also compatible with the demand of generic event streaming applications.

~ More in the [whitepaper](https://github.com/SmithSamuelM/Papers/blob/master/whitepapers/KERI_WP_2.x.web.pdf)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/delegated-identifier">extended KERI glossary</a>

[[def: delegatee, Delegatee]]

~ Entity that requests delegation during a delegation-based AID inception.

[[tref: toip1, delegation]]

[[def: delegator, Delegator]]

~ Entity that acknowledges delegation by adding the Delegatee AID into the KEL Entity during a delegation-based AID inception.

[[def: derivation-code, Derivation code]]

~ To properly extract and use the [[ref: public-key-infrastructure]] embedded in a [[ref: self-certifying-identifier]] we need to know the cryptographic _signing scheme_ used by the [[ref: key-pair]]. KERI includes this very compactly in the identifier, by replacing the pad character (a character used to fill a void to able to always end up with a fixed length public key) with a special character that encodes the derivation process. We call this the _derivation code_.

~ Mind you: The derivation code is not referring to derivation from a table for the code itself but how the body is derived via a cryptographic algorithm. The derivation code indicates what cryptographic algorithm was used to derive the body.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/derivation-code">extended KERI glossary</a>

[[def: designated-aliases, Designated aliases]]

~ An AID controller can designate aliases which are AID controlled identifiers such as a did:keri, did:webs, etc. The [[ref: AID]] controller issues a designated aliases attestation (no issuee) that lists the identifiers and manages the status through a registry anchored to their KEL. See the [designated aliases docs](https://weboftrust.github.io/schema/desig-aliases)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/designated-aliases">extended KERI glossary</a>

[[def: designated-authorized-representative, Designated authorized representative]]

~ Also 'DAR'. These are representatives of a Legal Entity that are authorized by the Legal Entity to act officially on behalf of the Legal Entity. DARs can authorize:
~ 1. vLEI Issuer Qualification Program Checklists
~ 2. execute the vLEI Issuer Qualification Agreement
~ 3. provide designate/replace Authorized vLEI Representatives ([[ref: authorized-vlei-representative]]s).

~ Paraphrased by @henkvancann from [source](https://www.gleif.org/vlei/introducing-the-vlei-ecosystem-governance-framework/2022-02-07_verifiable-lei-vlei-ecosystem-governance-framework-glossary-draft-publication_v0.9-draft.pdf) Draft vLEI Ecosystem Governance Framework Glossary.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/designated-authorized-representative">extended KERI glossary</a>

[[def: diger]]

~ A _primitive_ that represents a [[ref: digest]]. It has the ability to [[ref: verify]] that an input hashes to its raw value.  
~ [Source](https://github.com/WebOfTrust/cesride#terminology) by Jason Colburne
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/diger">extended KERI glossary</a>

[[def: dip]]

~ dip = delcept, delegated inception
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/dip">extended KERI glossary</a>

[[def: direct-mode, Direct mode]]

~ Two primary trust modalities motivated the KERI design, One of these is the _direct_ (one-to-one) mode, in which the identity controller establishes control via verified signatures of the controlling key-pair. The direct mode doesn't use witnesses nor [[ref: key-event-receipt-log]]s, but has direct (albeit intermittent) network contact with the validator.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/direct-mode">extended KERI glossary</a>

[[def: disclosee, Disclosee]]

~ a role of an entity that is a recipient to which an ACDC is disclosed. A Disclosee may or may not be the Issuee of the disclosed ACDC.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/disclosee">extended KERI glossary</a>

[[def: discloser, Discloser]]

~ a role of an entity that discloses an [[ref: authentic-chained-data-container]]. A Discloser may or may not be the Issuer of the disclosed ACDC.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/discloser">extended KERI glossary</a>

[[tref: toip1, discovery]]

[[def: dnd]]

~ Do Not Delegate is a flag/attribute for an AID, and this is default set to "you can delegate."

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/dnd">extended KERI glossary</a>

[[def: domain, Domain]]

~ a representation of a [[ref: primitive]] either Text (T), Binary (B) or Raw binary \(R).  
~ Source: Dr. S. Smith

~ Beware: outside of CESR but within the internet world, the term 'domain' mostly refers to the concept of a _domain name_.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/domain">extended KERI glossary</a>

[[def: drt]]

~ drt = deltate, delegated rotation

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/drt">extended KERI glossary</a>

[[def: dual-indexed-codes, Dual indexed codes]]

~ a context-specific coding scheme, for the common use case of thresholded multi-signature schemes in [[ref: CESR]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/dual-indexed-codes">extended KERI glossary</a>

[[def: dual-text-binary-encoding-format, Dual-text binary-encoding format]]

~ An encoding format that allows for both text and binary encoding format, which is fully interchangeable. The [[ref: composability]] property enables the round trip conversion en-masse of concatenated primitives between the text domain and binary domain while maintaining the separability of individual primitives.  
~ Read more in [source](https://github.com/trustoverip/tswg-cesr-specification/blob/main/draft-ssmith-cesr.md) of Samuel Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/dual-text-binary-encoding-format">extended KERI glossary</a>

[[def: duplicitous-event-log, Duplicitous event log, DEL]]

~ This is a record of inconsistent event messages produced by a given controller or witness with respect to a given [[ref: key-event-receipt-log]]. The duplicitous events are indexed to the corresponding event in a KERL. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/duplicitous-event-log">extended KERI glossary</a>

[[def: duplicity-detection, Duplicity detection]]

~ A mechanism to detect [[ref: duplicity]] in cryptographically secured event logs.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/duplicity-detection">extended KERI glossary</a>

[[def: duplicity, Duplicity]]

~ the existence of more than one version of a Verifiable [[ref: key-event-log]] for a given [[ref: AID]].  
~ Source: Dr. S.Smith, 2024

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/duplicity">extended KERI glossary</a>

[[def: edge, Edge]]

~ a top-level field map within an ACDC that provides edges that connect to other ACDCs, forming a labeled property graph (LPG).  
~ Source: Dr. S. Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/edge">extended KERI glossary</a>

[[def: end-role, End role]]

~ An end role is an authorization for one [[ref: AID]] to serve in a role for another [[ref: AID]].  

~ For example, declaring that your [[ref: agent]] [[ref: AID]] is serving in the role of [[ref: agent]] for your business AIDs.

~ Source: Phil Feairheller
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/end-role">extended KERI glossary</a>

[[def: end-verifiability, End-verifiability]]

~ a data item or statement may be cryptographically securely attributable to its source (party at the source end) by any recipient verifier (party at the destination end) without reliance on any infrastructure not under the verifier’s ultimate control.  
~ Source Dr. S.Smith

[[def: escrow-state, Escrow state]]

~ The current state of all the temporary storage locations (what events are waiting for what other information) that KERI protocol needs to  keep track of, due to its fully asynchronous nature.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/escrow-state">extended KERI glossary</a>

[[def: establishment-event, Establishment event]]

~ a [[ref: key-event]] that establishes or changes the key state which includes the current set of authoritative keypairs (key state) for an [[ref: AID]].  
~ Source: dr. S.Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/establishment-event">extended KERI glossary</a>

[[def: exchange-identifier, Exchange identifier]]

~ a cryptographically verifiable identifier used to represent a party in a data exchange. It facilitates secure attribution (authenticity), content protection (confidentiality), and may support privacy via uncorrelatable or pseudonymous metadata.

[[def: exn]]

~ exn = exchange

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/exn">extended KERI glossary</a>

[[def: exp]]

~ exp = expose, sealed data exposition

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/exp">extended KERI glossary</a>

[[def: field-map, Field map]]

~ A traditional `key:value` pair renamed to avoid confusing with the cryptographic use of the term 'key'.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/field-map">extended KERI glossary</a>

[[def: first-seen, First-seen]]

~ refers to the first instance of a [[ref: message]] received by any [[ref: witness]] or [[ref: watcher]]. The first-seen event is always seen, and can never be unseen. It forms the basis for [[ref: duplicity]] detection in KERI-based systems.  
~ Source: Dr. S.Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/first-seen">extended KERI glossary</a>

[[def: frame-code, Frame code]]

~ [[ref: framing-code]]

[[def: framing-code, Framing code, Framing codes]]

~ a code that delineates a number of characters or bytes, as appropriate, that can be extracted atomically from a [[ref: stream]].  
~ Source: Dr. S. Smith

[[def: full-disclosure, Full disclosure]]

~ a disclosure of an ACDC that discloses the full details of some or all of its field maps. In the context of [[ref: selective-disclosure]], Full Disclosure means detailed disclosure of the selectively disclosed attributes, not the detailed disclosure of all selectively disclosable attributes. In the context of [[ref: partial-disclosure]], Full Disclosure means detailed disclosure of the field map that was so far only partially disclosed.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/full-disclosure">extended KERI glossary</a>

[[def: fully-compact, Fully compact]]

~ The most compact form of an [[ref: ACDC]]. This is the only signed variant of an ACDC and this signature is anchored in a [[ref: transaction-event-log]] (TEL) for the ACDC.
~ This is one valid choice for an ACDC schema.   
~ This form is part of the [[ref: graduated-disclosure]] mechanism in ACDCs.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/fully-compact">extended KERI glossary</a>

[[def: fully-expanded, Fully expanded]]

~ The most user-friendly version of an [[ref: ACDC]] credential. It doesn't need to be signed and typically is not signed since the most compact version which is signed can be computed from this form and then the signature can be looked up in the [[ref: TEL]] of the ACDC in question. 

~ Regarding the graduated disclosure objective this form is the one with the highest amount of disclosure for a given node of an ACDC graph.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/fully-expanded">extended KERI glossary</a>

[[def: ghost-credential, Ghost credential]]

~ Is a valid credential within in a 90 days grace period (the revocation transaction time frame before it's booked to revocation registry). 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ghost-credential">extended KERI glossary</a>

[[def: GLEIF]]

~ Global Legal Entity Identifier Foundation, visit https://www.gleif.org/en

[[def: GLEIS]]

~ Global Legal Entity Identifier System
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/GLEIS">extended KERI glossary</a>

[[def: graduated-disclosure, Graduated disclosure]]

~ a disclosure of an [[ref: ACDC]] that does not reveal its entire content in the initial interaction with the recipient and, instead, partially or selectively reveals only the information contained within the ACDC necessary to further a transaction with the recipient. A Graduated disclosure may involve multiple steps where more information is progressively revealed as the recipient satisfies the conditions set by the [[ref: discloser]]. [[ref: compact-disclosure]], [[ref: partial-disclosure]], [[ref: selective-disclosure]], and [[ref: full-disclosure]] are all Graduated disclosure mechanisms.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/graduated-disclosure">extended KERI glossary</a>

[[def: graph-fragment, Graph fragment]]

~ An ACDC is a verifiable data structure and _part of a graph_, consisting of a node property and one or two edge proporties.

~ <img src="https://hackmd.io/_uploads/r1KDqKxzj.png" width="300" />
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/graph-fragment">extended KERI glossary</a>

[[def: group-code, Group code]]

~ [[ref: group-framing-code]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/group-code">extended KERI glossary</a>

[[def: group-count-codes, Group/Count codes]]

~ special Framing Codes that can be specified to support groups of Primitives which make them pipelinable.  Self-framing grouping using Count Codes is one of the primary advantages of composable encoding.  
~ Source: Dr. S.Smith

[[def: group-framing-code, Group framing code]]

~ special Framing Codes that can be specified to support groups of Primitives which make them pipelinable. Self-framing grouping using Count Codes is one of the primary advantages of composable encoding.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/group-framing-code">extended KERI glossary</a>

[[def: hab]]

~ A Hab is a keystore for one identifier. The Python implementation in [[ref: keripy]], also used by [[ref: keria]] uses [LMDB](http://www.lmdb.tech/doc/) to store key material and all other data.

~ Many Habs are included within and managed by a [[ref: habery]].
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/hab">extended KERI glossary</a>

[[def: habery, Habery]]

~ 'Hab' comes from ‘Habitat’. It’s a place where multi-sigs and AIDs are linked. Habery manages a collection of [[ref: hab]]. A Hab is a data structure (a Python object). A habery is also called a vault.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/habery">extended KERI glossary</a>

[[def: hierarchical-composition, Hierarchical composition]]

~ Encoding protocol that is composable in a hierarchy and enables [[ref: pipelining]] (multiplexing and de-multiplexing) of complex streams in either text or compact binary. This allows management at scale for high-bandwidth applications.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/hierarchical-composition">extended KERI glossary</a>

[[def: icp]]

~ icp = incept, inception
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/icp">extended KERI glossary</a>

[[tref: toip1, identity-assurance, Identity assurance]]

[[def: inception-event, Inception event]]

~ an [[ref: establishment-event]] that provides the incepting information needed to derive an AID and establish its initial Key state.  
~ Source [Sam Smith](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md#basic-terminology)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/inception-event">extended KERI glossary</a>

[[def: inception, Inception]]

~ The operation of creating an AID by binding it to the initial set of authoritative keypairs and any other associated information. This operation is made verifiable and duplicity evident upon acceptance as the inception event that begins the AID's KEL.  
~ Source [Sam Smith](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md#basic-terminology)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/inception">extended KERI glossary</a>

[[def: indexed-signature, Indexed signature]]

~ Also called _siger_. An indexed signature attachment is used when signing anything with a multi-key autonomic identifier. The index is included as part of the attachment, so a verifier knows which of the multiple public keys was used to generate a specific signature.  
~ Source:Philip Feairheller

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/indexed-signature">extended KERI glossary</a>

[[def: indirect-mode, Indirect mode]]

~ Two primary trust modalities motivated the KERI design, One of these is the _indirect_ (one-to-many) mode, which depends on witnessed key event receipt logs (KERL) as a secondary root-of-trust for validating events. This gives rise to the acronym KERI for key event receipt infrastructure.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/indirect-mode">extended KERI glossary</a>

[[def: information-theoretic-security, Information theoretic security, ITPS]]

~ the highest level of cryptographic security with respect to a cryptographic secret (seed, salt, or private key).  
~ Source: Dr. S.Smith

[[def: inquisitor, Inquisitor]]

~ In the [[ref: ACDC]] context it's a general term for someone (in a validating role) that launches an inquiry at some KERI [[ref: witness]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/inquisitor">extended KERI glossary</a>

[[def: Integrity]]

~ Integrity (of a message or data) means that the information is whole, sound, and unimpaired (not necessarily correct). It means nothing is missing from the information; it is complete and in intended good order.  
~ Source: Neil Thomson

~ ~In KERI's "security first" approach Authenticity includes _technical integrity_ of data involved. This includes:
~ 1. [[ref:internal-inconsistency]]
~ 2. External consistency or [[ref:duplicity]] evident

~ Note: Integrity in ACDCs is "self-verifying": the [[ref:self-addressing-identifier)]] that is contained in the data is also the of hash of the data.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/integrity">extended KERI glossary</a>

[[def: interaction-event, Interaction event]]

~ Non-establishment Event that anchors external data to the key-state as established by the most recent prior establishment event.  
~ Source [Sam Smith](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md#basic-terminology)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/interaction-event">extended KERI glossary</a>

[[def: interactive-authentication-design, Interactive authentication design]]

~ A group of approaches having an interactive mechanism that requires a set of requests and responses or challenge responses with challenge response replies for secure authentication.  
~ More in [source](https://hackmd.io/ZbVAbNK1SPyT90-oNwN_cw) Keri Request Authentication Mechanism (KRAM) by Samuel Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/interactive-authentication-design">extended KERI glossary</a>

[[def: interceptor, Interceptor]]

~ a [[ref: keria]] class that allows to push events that are happening inside the cloud agent to other backend processes.
~ It is similar to the notifier class but it is used to "notify" other web services.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/interceptor">extended KERI glossary</a>

[[def: interleaved-serialization, Interleaved serialization]]

~ Serializations of different types interleaved in an overarching format

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/interleaved-serialization">extended KERI glossary</a>

[[def: IPEX]]

~ [[ref: issuance-and-presentation-exchange-protocol]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/IPEX">extended KERI glossary</a>

[[def: iss]]

~ iss = vc issue, verifiable credential issuance

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/iss">extended KERI glossary</a>

[[def: issuance-and-presentation-exchange-protocol, issuance and presentation exchange protocol, IPEX]]

~ provides a uniform mechanism for the issuance and presentation of ACDCs in a securely attributable manner. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/issuance-and-presentation-exchange-protocol">extended KERI glossary</a>

[[def: issuance-event, Issuance event]]

~ The initial transaction event log event anchored to the issuing AID’s key event log that represents the issuance of an ACDC credential.  
~ Source: Philip Feairheller.

~ It's a sort of "[[ref: inception-event]]" of a verifiable credential.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/issuance-event">extended KERI glossary</a>

[[def: issuance-exchange, Issuance exchange]]

~ A special case of a [[ref: presentation-exchange]] where the [[ref: discloser]] is the [[ref: issuer]] of the origin (Primary) ACDC of the [[ref: directed-acyclic-graph]] formed by the set of chained [[ref: authentic-chained-data-container]]s so disclosed.

~ In an issuance exchange, when the origin ACDC has an [[ref: issuee]], the [[ref: disclosee]] MAY also be the origin ACDC's Issuee.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/issuance-exchange">extended KERI glossary</a>

[[def: issuee, Issuee]]

~ a role of an entity to which the claims of an ACDC are asserted.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/issuee">extended KERI glossary</a>

[[def: issuer, Issuer]]

~ a role of an entity that asserts claims and creates an ACDC from these claims.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/issuer">extended KERI glossary</a>

[[def: ixn]]

~ [[ref: JSON]] field name (attribute) for Interaction Event; its content (value) contains a hash pointer. All [[ref: transaction-event-log]] events are anchored in a [[ref: key-event-log]] in either ixn ([[ref: interaction-event]]) or [[ref: rot]] ([[ref: rotation-event]]s). This is the foundation enabling a verifiable credential protocol to be built on top of KERI.  
~ [Source](https://kentbull.com/2023/03/09/keri-tutorial-series-treasure-hunting-in-abydos-issuing-and-verifying-a-credential-acdc/) Kent Bull 2023

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ixn">extended KERI glossary</a>

[[def: judge, Judge]]

~ A judge is an entity or component that examines the entries of one or more [[ref: key-event-receipt-log]] and DELs of a given identifier to validate that the event history is from a non-[[ref: duplicity]] controller and has been witnessed by a sufficient number of non-duplicitous [[ref: witness]] such that it may be trusted or conversely not-trusted by a [[ref: validator]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/judge">extended KERI glossary</a>

[[def: juror, Juror]]

~ A juror has the basic task of performing [[ref: duplicity]] detection on events and event receipts.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/juror">extended KERI glossary</a>

[[def: jury, Jury]]

~ The jury is the set of entities or components acting as [[ref: juror]].
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/jury">extended KERI glossary</a>

[[def: KA2CE]]

~ [[ref: keri-agreement-algorithm-for-control-establishment]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KA2CE">extended KERI glossary</a>

[[def: KAACE]]

~ [[ref: keri-agreement-algorithm-for-control-establishment]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KAACE">extended KERI glossary</a>

[[def: KAPI]]

~ Application programmer interfaces (APIs) for the various components in the KERI ecosystem such as Controllers, Agents, Witnesses, Watchers, Registrars etc need by which they can share information. The unique properties of the KERI protocol require APIs that preserve those properties. We call the set of APIs the KERI API.  
~ [Source Kapi Repo](https://github.com/WebOfTrust/kapi/blob/main/kapi.md)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KAPI">extended KERI glossary</a>

[[def: KAWA]]

~ [[ref: keri’s-algorithm-for-witness-agreement]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KAWA">extended KERI glossary</a>

[[def: keep]]

~ Is KERI's and ACDC's user interface that uses the keripy agent for its backend. It uses the REST API exposed from the keripy agent.  
~ Source: Philip Feairheller

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keep">extended KERI glossary</a>

[[def: KEL]]

~ A Key Event Log.
~ [[ref: key-event-log]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KEL">extended KERI glossary</a>

[[def: keri-agreement-algorithm-for-control-establishment, keri agreement algorithm for control establishment, KAWA]]

~ Agreement on an event in a key event log [[ref: KEL]] means each [[ref: witness]] has observed the exact version of the event and each witness’ [[ref: receipt]] has been received by every other witness.

~ Control establishment means that the set of agreeing witnesses, along with the controller of the identifier and associated keypairs, create a verifiable way to establish control authority for an identifier by reading all of the events in the KEL that have been agreed upon by the witnesses and the controller.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keri-agreement-algorithm-for-control-establishment">extended KERI glossary</a>

[[def: keri-command-line-interface, KERI command-line interface]]

~ Command line tool used to create identifiers, manage keys, query for KELs and participate in delegated identifiers or multi-signature group identifiers.  It also includes operations for running witnesses, watchers and cloud agents to establish a cloud presence for any identifier.

~ Most commands require a “name” parameter which references a named Habitat (think wallet) for performing the operation.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keri-command-line-interface">extended KERI glossary</a>

[[def: keri-event-stream, KERI event stream]]

~ A stream of verifiable KERI data, consisting of the [[ref: key-event-log]] and other data such as a [[ref: transaction-event-log]]. This data is a CESR event stream (TODO: link to IANA application/cesr media type) and may be serialized in a file using [[ref: composable-event-streaming-representation]] encoding. We refer to these _CESR stream resources_ as KERI event streams to simplify the vocabulary.

~ Source `did:webs` [ToIP specification](https://trustoverip.github.io/tswg-did-method-webs-specification/index.html)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keri-event-stream">extended KERI glossary</a>

[[def: keri-improvement-doc, KERI improvement doc, KID]]

~ These docs are modular so teams of contributors can independently work and create PRs of individual KIDs; KIDs answer the question "how we do it". We add commentary to the indivudual KIDs that elaborate on the why. It has been split from the how to not bother implementors with the why.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keri-improvement-doc">extended KERI glossary</a>

[[def: keri-ox, KERI ox]]

~ The RUST programming-language implementation of the [KERI](https://github.com/trustoverip/acdc/wiki/KERI) protocol.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keri-ox">extended KERI glossary</a>

[[def: keri-request-authentication-method, KERI request authentication method, KRAM]]

~ All requests from a web client must use KRAM (KERI Request Authentication Method) for replay attack protection. The method is essentially based on each request body needing to include a date time string field in ISO-8601 format that must be within an acceptable time window relative to the server's date time. See the [KRAM Github repo](https://github.com/WebOfTrust/kram/blob/main/README.md)

~ Source [SKWA GitHub repo](https://github.com/WebOfTrust/skwa), more info in [HackMD.io write-up](https://hackmd.io/ZbVAbNK1SPyT90-oNwN_cw)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keri-request-authentication-method">extended KERI glossary</a>

[[def: keri-suite-search-engine, KERI suite search engine, KERISSE]]

~ KERISSE is the Docusaurus [self-education site](https://weboftrust.github.io/WOT-terms/) of Web-of-Trust GitHub repo with Typesense search facilities. Because of its focus on well-versed developers in the field of [[ref: SSI]] and the support of their journey to understand the structure of the code and how things work in the [[ref: keri-suite]] it's more a search engine that drills down on documentation.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keri-suite-search-engine">extended KERI glossary</a>

[[def: keri-suite, KERISuite, KERI suite]]

~ An open-source codebase centered on KERI, with supporting tools like ACDC, CESR, OOBI, KERIA, and Signify — all designed to work together for secure, decentralized key management and identity infrastructure.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keri-suite">extended KERI glossary</a>

[[def: KERI]]

~ [[ref: key-event-receipt-infrastructure]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KERI">extended KERI glossary</a>

[[def: KERIA-agent, KERIA agent]]

~ An [[ref: agent]] in [[ref: keria]] terms, is an instance of a keystore ([[ref: hab]]) that runs in a given instance of the KERIA agent server.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KERIA-agent">extended KERI glossary</a>

[[def: KERIA]]

~ KERI Agent in the cloud. The KERIA service will expose 3 separate HTTP endpoints on 3 separate network interfaces.

~ 1. Boot Interface - Exposes one endpoint for Agent Worker initialization.
~ 2. Admin Interface - The REST API for command and control operations from the Signify Client.
~ 3. KERI Protocol Interface - CESR over HTTP endpoint for KERI protocol interactions with the rest of the world.

~ More at [Source Github repo](https://github.com/WebOfTrust/keria/blob/main/docs/protocol.md)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KERIA">extended KERI glossary</a>

[[def: keride, Keride]]

~ is a _Rust_ programming language library for [[ref: key-event-receipt-infrastructure]]. Among its features
~  is [[ref: CESR]], signing, prefixing, pathing, and parsing.  
~ More on [Github repo](https://github.com/WebOfTrust/keride)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keride">extended KERI glossary</a>

[[def: keridemlia, Keridemlia]]

~ It is a contraction of [[ref: key-event-receipt-infrastructure]] and [Kademlia](https://en.wikipedia.org/wiki/Kademlia). It's the distributed database of Witness IP-addresses based on a [[ref: distributed-hash-table]]. It also does the CNAME - stuff that [[ref: domain-name]] Services (DNS) offers for KERI: the mapping between an identifier and it's controller AID stored in the KEL to its current wittness AID and the wittness AID to the IP address.  
~ (@henkvancann)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keridemlia">extended KERI glossary</a>

[[def: kerific]]

~ *kerific* is a front plugin or extension that currently only works for Chrome and Brave. It matches words in any text on the web that is parseable for kerific and offers buttons to various glossaries and definitions in the [[ref: self-sovereign-identity]] field.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/kerific">extended KERI glossary</a>

[[def: KERIMask]]

~ A wallet similar to _MetaMask_, the manifestation will be a browser extension and it will connect to KERIA servers in order for a person to control AIDs from their browser.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KERIMask">extended KERI glossary</a>

[[def: keripy]]

~ The Python programming-language implementation of the [[ref: KERI]] protocol.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keripy">extended KERI glossary</a>

[[def: keris-algorithm-for-witness-agreement, KERI's algorithm for witness agreement, KAWA]]

~ a type of Byzantine Fault Tolerant ([[ref: byzantine-fault-tolerance]]) algorithm.  
~ Source: Dr. S.Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/keri’s-algorithm-for-witness-agreement">extended KERI glossary</a>

[[def: KERISSE]]

~ [[ref: keri-suite-search-engine]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KERISSE">extended KERI glossary</a>

[[def: KERL]]

~ [[ref: key-event-receipt-log]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KERL">extended KERI glossary</a>

[[def: kever]]

~ Kever is a key event verifier.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/kever">extended KERI glossary</a>

[[def: key-event-log, Key event log, KEL]]

~ a Verifiable data structure that is a backward and forward chained, signed, append-only log of key events for an AID. The first entry in a KEL must be the one and only Inception event of that AID.  
~ Source [Sam Smith](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md#basic-terminology)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/key-event-log">extended KERI glossary</a>

[[def: key-event-message, Key event message]]

~ Message whose body is a key event and whose attachments may include signatures on its body.  
~ Source [Sam Smith](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md#basic-terminology)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/key-event-message">extended KERI glossary</a>

[[def: key-event-receipt-infrastructure, Key event receipt infrastructure, KERI]]

~ or the KERI protocol, is an identity system-based secure overlay for the Internet.  
~ Source: Dr. S.Smtih

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/key-event-receipt-infrastructure">extended KERI glossary</a>

[[def: key-event-receipt-log, Key event receipt log, KERL]]

~ a key event receipt log is a [[ref: kel]] that also includes all the consistent key event receipt [[ref: message]]s created by the associated set of witnesses.
~ Source: Dr. S.Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/key-event-receipt-log">extended KERI glossary</a>

[[def: key-event-receipt, Key event receipt]]

~ message whose body references a Key event and whose attachments must include one or more signatures on that Key event.   
~ Source [Sam Smith](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md#basic-terminology)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/key-event-receipt">extended KERI glossary</a>

[[def: key-event, Key event]]

~ See the more general TrustoverIP concept of key-event: [[xref: toip1, key-event, Key event]]

~ Concretely, it is the serialized data structure of an entry in the Key event log ([[ref: KEL]]) for an [AID]( [[ref: autonomic-identifier]]). Abstractly, the data structure itself. Key events come in different types and are used primarily to establish or change the [[ref: authoritative]] set of keypairs and/or anchor other data to the authoritative set of keypairs at the point in the KEL actualized by a particular entry.    
~ Source [Sam Smith](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md#basic-terminology)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/key-event">extended KERI glossary</a>

[[def: Key-state, Key state]]

~ a set of currently authoritative keypairs for an AID and any other information necessary to secure or establish control authority over an AID. This includes current keys, prior next key digests, current thresholds, prior next thresholds, witnesses, witness thresholds, and configurations. A key-state of an AID is first established through an inception event and may be altered by subsequent rotation events.  
~ Source: Dr. S.Smith

~ Also see [[ref:validator]]

[[def: kli]]

~ [[ref: keri-command-line-interface]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/kli">extended KERI glossary</a>

[[def: KRAM]]

~ [[ref: keri-request-authentication-method]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/KRAM">extended KERI glossary</a>

[[def: ksn]]

~ ksn = state, key state notice

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ksn">extended KERI glossary</a>

[[def: ledger-backer, Ledger backer]]

~ A [[ref: witness]] in KERI that is ledger-registered. It's a type of [[ref: backer]] that proof its authenticity by a signing key anchored to the public key of a data item on a (public) blockchain.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ledger-backer">extended KERI glossary</a>

[[def: legitimized-human-meaningful-identifier, Legitimized human-meaningful identifier, LID]]

~ An [[ref:AID]] and its associated self-certifying trust basis gives rise to a trust domain for associated cryptographically verifiable non-repudiable statements. Every other type of identifier including human meaningful identifiers may then be secured in this resultant trust domain via an [[ref:end-verifiable]] [[authorization]]. This authorization legitimizes that human meaningful identifier as an LID through its association with an AID. The result is a secured trust domain specific identifier couplet of aid|lid.  
~ Source Dr. S.Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/legitimized-human-meaningful-identifier">extended KERI glossary</a>

[[def: listed-identifier, Listed identifier]]

~ Is a list in an [[ref: authentic-chained-data-container]] of authorised did:webs identifier + method; the list appears in the metadata of the did:webs DID-doc.  
~ Source: paraphrased Samuel Smith, Zoom meeting _KERI dev_ Thursday Nov 9 2023
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/listed-identifier">extended KERI glossary</a>

[[def: live-attack, Live attack]]

~ an attack that compromises either the current signing keys used to sign non-establishment events or the current pre-rotated keys needed to sign a subsequent establishment event. See (Security Properties of Prerotation)[#live-attacks].  
~ Source: Dr. S.Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/live-attack">extended KERI glossary</a>

[[def: locked-state, Locked state]]

~ The default status a KERI data store is in once it has been created using a [[ref: passcode]]; it is by default encrypted.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/locked-state">extended KERI glossary</a>

[[def: management-transaction-event-log, Management TEL, Management transaction event log]]

~ A 'management [[ref: transaction-event-log]]' will signal the creation of the _Virtual Credential Registry [[ref: VCR]]_ and track the list of _Registrars_ that will act as _[[ref: backer]]_ for the individual _ transaction event logs (TELs)_ for each [[ref: virtual-credential]] (VC).
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/management-transaction-event-log">extended KERI glossary</a>

[[def: message, message]]

~ a serialized data structure that comprises its body and a set of serialized data structures that are its attachments. Attachments may include but are not limited to signatures on the body.  
~ Source: Dr. S.Smith

~ Also see: [[xref: toip1, message]] in ToIP main glossary.

[[def: moobi]]

~ Multi [[ref: OOBI]] would allow to share a bunch of different end-points (oobis) all at once. A way for a single store to share multiple endpoints for that store. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/moobi">extended KERI glossary</a>

[[def: most-compact, Most compact]]

~ An [[ref: ACDC]] that, for a given level of disclosure, is as compact as it can be, which means
~ - it has the [[ref: SAID]]s for each section that are not disclosed 
~ - it has expanded sections that are disclosed 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/most-compact">extended KERI glossary</a>

[[def: multi-valent, Multi valent]]

~ A [[ref: delegator]] may have multiple [[ref: delegate]], thereby enabling elastic horizontal scalability. Multiple delegates from a single delegator. Furthermore, each delegate may act as a delegator for its own delegates to form a *nested delegation tree*.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/multi-valent">extended KERI glossary</a>

[[def: naive-conversion, Naive conversion]]

~ Non-CESR Base64 conversion. How people are used to using the Base64 encode and decode.  Without [[ref: pre-pad]]ding etc all the stuff CESR does to ensure aligns on 24 bit boundaries so [[ref: CESR]] never uses the '=' pad character. But naive [[ref: base64]] will pad if the length is not 24 bit aligned.  
~ Source: Samuel Smith in [issue 34](https://github.com/WebOfTrust/ietf-cesr/issues/34)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/naive-conversion">extended KERI glossary</a>

[[def: ndigs]]

~ Digests of public keys, not keys themselves. The reason to use ndigs is to prove control over public keys or to hide keys. It's used in Keripy and consists of a list of qualified base64 digests of public rotation key derivations.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ndigs">extended KERI glossary</a>

[[def: nested-cooperative-delegated-identifiers, Nested cooperative delegated identifiers]]

~ In KERI delegations are cooperative, this means that both the delegator and delegate must contribute to a delegation. The delegator creates a cryptographic commitment in either a rotation or interaction event via a seal in a delegated establishment event. The delegate creates a cryptographic commitment in its establishment event via a seal to the delegating event. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/nested-cooperative-delegated-identifiers">extended KERI glossary</a>

[[def: next-threshold, Next threshold]]

~ represents the number or fractional weights of signatures from the given set of next keys required to be attached to a [Message](https://trustoverip.github.io/kswg-keri-specification/#term:message) for the [Message](https://trustoverip.github.io/kswg-keri-specification/#term:message) to be considered fully signed.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/next-threshold">extended KERI glossary</a>

[[def: non-establishment-event, Non-establishment event]]

~ a Key event that does not change the current Key state for an AID. Typically, the purpose of a Non-establishment event is to anchor external data to a given Key state as established by the most recent prior Establishment event for an AID.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/non-establishment-event">extended KERI glossary</a>

[[def: non-interactive-authentication-design, Non-interactive authentication design]]

~ A group of approaches having non-interactive mechanisms that pose unique problems because they do not allow a challenge response reply handshake. A request is submitted that is self-authenticating without additional interaction. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/non-interactive-authentication-design">extended KERI glossary</a>

[[tref: toip1, non-repudiable, Non-repudiable]]

[[tref: toip1, non-transferable-identifier, Non-transferable identifier]]

[[def: OOBI]]

~ [[ref: out-of-band-introduction]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/OOBI">extended KERI glossary</a>

[[def: opcode, Opcode]]

~ Opcodes are meant to provide stream processing instructions that are more general and flexible than simply concatenated primitives or groups of primitives. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/opcode">extended KERI glossary</a>

[[def: operator, Operator]]

~ an optional field map in the Edge section that enables expression of the edge logic on edge subgraph as either a unary operator on the edge itself or an m-ary operator on the edge group.  
~ Source: Dr. S.Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/operator">extended KERI glossary</a>

[[def: out-of-band-introduction, Out-of-band introduction, OOBI]]

~ Out-of-band Introductions (OOBIs) are discovery and validation of IP resources for [[ref: key-event-receipt-infrastructure]] autonomic identifiers. **Discovery via URI, trust via KERI.**

~ The simplest form of a KERI OOBI is a namespaced string, a tuple, a mapping, a structured message, or structured attachment that contains both a KERI AID and a URL. The OOBI associates the URL with the AID. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/out-of-band-introduction">extended KERI glossary</a>

[[def: parside, Parside]]

~ is a bunch of generators. Responsible for pulling out a stream of bits from a CESR stream and parse it.
~ Sam Smith suggested for Parside to not iterate stuff, only parse chunks delimited by the [[ref: count-code]]. (Source Cesride: meeting Feb 2 2023)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/parside">extended KERI glossary</a>

[[def: partial-disclosure, Partial disclosure]]

~ a disclosure of an ACDC that partially discloses its field maps using Compact Disclosure. The Compact Disclosure provides a cryptographically equivalent commitment to the yet-to-be-disclosed content, and the later exchange of the uncompacted content is verifiable to an earlier Partial Disclosure. Unlike Selective disclosure, a partially disclosable field becomes correlatable to its encompassing block after its Full Disclosure.  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/partial-disclosure">extended KERI glossary</a>

[[def: partial-pre-rotation, Partial pre-rotation]]

~ [[ref: partial-rotation]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/partial-pre-rotation">extended KERI glossary</a>

[[def: partial-rotation, Partial rotation]]

~ The pre-rotation mechanism supports partial pre-rotation or **more exactly partial rotation of pre-rotated keypairs**. It's a rotation operation on a set of pre-rotated keys that may keep some keys in reserve (i.e unexposed) while exposing others as needed.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/partial-rotation">extended KERI glossary</a>

[[def: pathing, Pathing]]

~ It was designed to sign portions of a credential aimed at complex cases like 
~ - a credential embedded in another credential
~ - multiple signers, only signing portions of a credential (partial signing)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/pathing">extended KERI glossary</a>

[[def: percolated-discovery, Percolated discovery]]

~ a discovery mechanism for information associated with an AID or a SAID, which is based on Invasion Percolation Theory. Once an entity has discovered such information, it may in turn share what it discovers with other entities. Since the information so discovered is end-verifiable, the percolation mechanism and percolating intermediaries do not need to be trusted.  
~ Source: Dr. S. Smith

~ [[ref: percolated-information-discovery]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/percolated-discovery">extended KERI glossary</a>

[[def: percolated-information-discovery, Percolated information discovery, PID]]

~ In the [[ref: OOBI]] protocol, a discovery mechanism for the [[ref: KERI]] and the [[ref: ACDC]] protocols is provided by a bootstrap that enables Percolated Information Discovery (PID), which is based on Invasion Percolation Theory.

~ After related information for discovery and verification is bootstrapped from the OOBI, subsequent authorization is non-interactive, thus making it highly scalable. This provides what we call zero-trust percolated discovery or speedy percolated discovery. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/percolated-information-discovery">extended KERI glossary</a>

[[def:  perfect-security, Perfect security]]

~ a special case of Information theoretic security [[ref: ITPS]]  
~ Source: Dr. S.Smith

[[tref: toip1, persistent-identifier, Persistent identifier]]

[[def: pre-rotation, Pre-rotation]]

~ Cryptographic commitment to next rotated key set in previous rotation or [[ref: inception-event]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/pre-rotation">extended KERI glossary</a>

[[def: prefix, Prefix]]

~ A prefix that is composed of a basic Base-64 (URL safe) derivation code pre-pended to Base-64 encoding of a basic public digital signing key.  
~ Including the derivation code in the prefix binds the derivation process along with the public key to the resultant identifier. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/prefix">extended KERI glossary</a>

[[def: presentation-exchange, Presentation exchange]]

~ An exchange that provides disclosure of one or more [[ref: authentic-chained-data-container]]s between a Discloser and a Disclosee.

~ A presentation exchange is the process by which [[ref: authenticity]] information may be exchanged between two parties, namely, the [[ref: discloser]] and [[ref: disclosee]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/presentation-exchange">extended KERI glossary</a>

[[def: primary-root-of-trust, Primary root-of-trust]]

~ In KERI a [[ref: root-of-trust]] that is cryptographically verifiable all the way to its current controlling key pair in a PKI. 

~ The characteristic _primary_ is one-on-one related to the **entropy** used for the creation of (the seed of) the private keys.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/primary-root-of-trust">extended KERI glossary</a>

[[def: prior-next-key-list, prior next key list]]

~ the list of unblinded public keys taken from the blinded key digest list from the most recent prior [[ref: Establishment event]].

[[def: prior-next-threshold, prior next threshold]]

~ the next threshold from the most recent prior [[ref: Establishment event]]

[[def: privacy]]

~ ~Privacy is primarily about control over the disclosure of who participated in the conversation (non-content metadata = identifiers). More specifically, privacy is about managing exploitably correlatable identifiers, not merely identifiers of who
~ but also any other type of identifier in non-content metadata, including conversation (interaction) identifiers.

~ Also see: [[ref: private]]

[[def: private]]

~ ˜The parties to a conversation are only known by the parties to that conversation.

~ Also see: [[ref: privacy]]

[[def: proem, Proem]]

~ A "proem" is an introductory statement, preamble, or preface. It sets the stage for the content that follows, often providing context, framing the discussion, or outlining the purpose and scope of the material. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/proem">extended KERI glossary</a>

[[def: promiscuous-mode, Promiscuous mode]]

~ It is the mode a [[ref: watcher]] runs in. A watcher uses the same code as a [[ref: witness]]. However a watcher does so "lacking standards of selection; acting without careful judgment; indiscriminate". Or "Showing little forethought or critical judgment; casual."  
~ [Source](https://www.wordnik.com/words/promiscuous)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/promiscuous-mode">extended KERI glossary</a>

[[def: proof-of-authorship, Proof of authorship]]

~ Proof that somebody or something has originally created certain content. It's about _data_'s inception. Whereas [[ref: proof-of-authority]] is about _rights_ attached to this data.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/proof-of-authorship">extended KERI glossary</a>

[[def: provenanced, Provenanced]]

~ The act of verifying [[ref: authenticity]] or quality of documented history or origin of something.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/provenanced">extended KERI glossary</a>

[[def: PTEL]]

~ [[ref: public-transaction-event-log]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/PTEL">extended KERI glossary</a>

[[def: public-transaction-event-log, Public transaction event log, PTEL]]

~ is a public hash-linked data structure of transactions that can be used to track state anchored to a [[ref: key-event-log]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/public-transaction-event-log">extended KERI glossary</a>

[[def: public-verifiable-credential-registry, Public verifiable-credential registry]]

~ is a form of a [Verifiable Data Registry](https://github.com/trustoverip/toip/wiki/credential-registry) that tracks the issuance/revocation state of credentials issued by the controller of the [[ref: key-event-log]]. Two types of TELs will be used for this purpose: [[ref: management-transaction-event-log]] and [[ref: virtual-credential-transaction-event-log]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/public-verifiable-credential-registry">extended KERI glossary</a>

[[def: qry]]

~ qry = query

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/qry">extended KERI glossary</a>

[[def: quadlet, Quadlet]]

~ a group of 4 characters in the T domain and equivalently in triplets of 3 bytes each in the B domain used to define variable size.  
~ Source: Dr. S. Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/quadlet">extended KERI glossary</a>

[[def: qualified, Qualified]]

~ When qualified, a cryptographic primitive includes a prepended derivation code (as a [[ref: proem]]), that indicates the cryptographic algorithm or suite used for that derivation. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/qualified">extended KERI glossary</a>

[[def: rct]]

~ rct = receipt

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/rct">extended KERI glossary</a>

[[def: read-update-nullify, Read update nullify, Read Update Nullify, RUN]]

~ Read, update, nullify are a set of actions you (or a server) can take on data. "Read" means to view it, "update" means to change it, and "nullify" means to invalidate it, but not "Delete" it. Mind you, there's also no "Create".

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/read-update-nullify">extended KERI glossary</a>

[[def: receipt-log, Receipt log]]

~ ordered record of all key event receipts for a given set of witnesses.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/receipt-log">extended KERI glossary</a>

[[def: receipt, Receipt]]

~ event message or reference with one or more witness signatures.

~ See Also:  
~ [[ref: key-event-receipt]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/receipt">extended KERI glossary</a>

[[def: receiver, Receiver]]

~ the receiver (recipient) of an exchange message. The receiver is a controller on its associated [[ref: KEL]] but is not the sender of the exchange message.

~ a receiver is a component that listens for and processes out-of-band messages, such as events or credentials, delivered via a mailbox system. It routes these messages to appropriate handlers for secure, asynchronous communication between [[ref: KERI agent]]s.

[[def: reconciliation, Reconciliation]]

~ Reconciliation is the process in which you decide to accept a fork of the [[ref: key-event-log]] or not.  
~ Source: Samuel Smith, Zoom meeting Jan 2 2024.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/reconciliation">extended KERI glossary</a>

[[def: redundant-credential, Redundant credential]]

~ Multiple credentials issued by the same issuer (e.g. a [[ref: QVI]]). They do not have anything to do with each other. They are independently valid.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/redundant-credential">extended KERI glossary</a>

[[def: registrar, Registrar]]

~ identifiers that serve as backers for each [[ref: transaction-event-log]] (TEL) under its provenance. This list of Registrars can be rotated with events specific to a certain type of TEL. In this way, a Registrar is analogous to a [[ref: Backer]] in KERI KELs and Registrar lists are analogous to Backer lists in KERI KELs.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/registrar">extended KERI glossary</a>

[[def: registration-interaction, Registration interaction]]

~ Setup/Registration interaction, new AID and authorization to establish access control. You present a ([[ref: vLEI]]) credential. You don't want that captured and misused. Narrowing the scope to a certain role (e.g. Document Submitter) is a pre-registration via [[ref: delegation]] authority.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/registration-interaction">extended KERI glossary</a>

[[def: reputation, Reputation]]

~ Consistent behaviour over time on the basis of which anyone else makes near-future decisions.  
~ Source: Samuel Smith at IIW37.

~ Also see TrustoverIP definition: [[xref:toip1, reputation]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/reputation">extended KERI glossary</a>

[[tref: toip1, reputational-trust, Reputational trust]]

[[def: reserve-rotation, Reserve rotation]]

~ One important use case for [[ref: partial-rotation]] is to enable pre-rotated key pairs designated in one [[ref: establishment-event]] **to be held in reserve and not exposed** at the next (immediately subsequent) establishment event.  
~ Source [IETF-KERI draft 2022](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md) by Samual Smith.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/reserve-rotation">extended KERI glossary</a>

[[def: rev]]

~ rev = vc revoke, verifiable credential revocation

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/rev">extended KERI glossary</a>

[[def: revocation-event, Revocation event]]

~ An event that revokes [[ref: control-authority]] over an [[ref: identifier]]. From that point in time the authoritative key-pairs at hand are not valid anymore.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/revocation-event">extended KERI glossary</a>

[[def: root-autonomic-identifier, Root autonomic identifier, RID]]

~ An entity may provide the [[ref: root-of-trust]] for some ecosystem (with delegation )via its root [[ref: AID]]. Let’s call this the _RID_ for "root AID". The RID must be protected using the highest level of [[ref: security]] in its [[ref: key-management]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/root-autonomic-identifier">extended KERI glossary</a>

[[def: rot]]

~ [[ref: JSON]] field name (attribute) for Rotation Event; its content (value) contains a hash pointer. All [[ref: transaction-event-log]] events are anchored in a [[ref: key-event-log]] in either ixn ([[ref: interaction-event]]) or [[ref: rot]] ([[ref: rotation-event]]s). This is the foundation enabling a verifiable credential protocol to be built on top of KERI.  
~ [Source](https://kentbull.com/2023/03/09/keri-tutorial-series-treasure-hunting-in-abydos-issuing-and-verifying-a-credential-acdc/) Kent Bull 2023

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/rot">extended KERI glossary</a>

[[def: rotation-authority, Rotation authority]]

~ The (exclusive) right to rotate the authoritative key pair and establish changed control authority.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/rotation-authority">extended KERI glossary</a>

[[def: rotation-event, Rotation event]]

~ an Establishment Event that provides the information needed to change the Key state, which includes a change to the set of [[ref: authoritative]] keypairs for an AID.  
~ Source: Dr. S.Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/rotation-event">extended KERI glossary</a>

[[def: rotation, Rotation]]

~ The operation of revoking and replacing the set of [[ref: authoritative]] [[ref: key-pair]] for an [[ref: AID]]. This operation is made verifiable and [[ref: duplicity]] evident upon acceptance as a rotation event that is appended to the AID's [[ref: KEL]].    
~ Source [Sam Smith](https://github.com/WebOfTrust/ietf-keri/blob/main/draft-ssmith-keri.md#basic-terminology)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/rotation">extended KERI glossary</a>

[[def: routed-exchange-message, Routed exchange message]]

~ is a KERI protocol message that allows one controller (sender) to transmit a confidential message to another controller (receiver) through one or more intermediaries (routers), while preserving authenticity (non-repudiation) and enabling confidentiality (through encryption), but potentially sacrificing privacy depending on routing visibility.

[[def: rpy]]

~ rpy = reply

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/rpy">extended KERI glossary</a>

[[def: rules, Rules]]

~ a top-level field map within an ACDC that provides a legal language as a [Ricardian Contract](https://en.wikipedia.org/wiki/Ricardian_contract), which is both human and machine-readable and referenceable by a cryptographic digest.  
~ Source: Dr. S. Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/rules">extended KERI glossary</a>

[[def: run-off-the-crud, Run off the crud]]

~ _RUN off the [[ref: CRUD]]_ is an alternative to the traditional [[ref: CRUD]] approach to defining basic operations on resources in data management systems (e.g., databases, APIs). RUN stands for Read, Update, Nullify and bears a nuanced approach to deletion.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/run-off-the-crud">extended KERI glossary</a>

[[def: RUN]]

~ The acronym for the new peer-to-peer end-verifiable monotonic update policy is RUN (**Read, Update, Nullify**). 

~ RUN as opposed to [[ref: CRUD]] which is the traditional client-server database update policy.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/RUN">extended KERI glossary</a>

[[def: SAD]]

~ [[ref: self-addressing-data]] and its synomym in KERI context [[ref: self-addressed-data]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/SAD">extended KERI glossary</a>

[[def: SAID]]

~ [[ref: self-addressing-identifier]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/SAID">extended KERI glossary</a>

[[def: sally, Sally]]

~ is an implementation of a verification service and acting as a reporting server. It is purpose-built software for the vLEI ecosystem to allow participants in the vLEI ecosystem present credentials, so the [[ref: GLEIF]] Reporting API can show what [[ref: vLEI]] are; issued to [[ref: legal-entity]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/sally">extended KERI glossary</a>

[[def: salter, Salter]]

~ A primitive that represents a [[ref: seed]]. It has the ability to generate new [[ref: signer]]s.  
~ [Source](https://github.com/WebOfTrust/cesride#terminology) by Jason Colburne
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/salter">extended KERI glossary</a>

[[def: salty-nonce-blinding-factor, Salty nonce blinding factor]]

~ For ease of sharing a secret and hiding information with this secret of Blindable State TELs we use a Salty Nonce Blinding Factor. You’d like to hide the state of certain credentials to some verifiers in the future, while keeping the state verifiable for others.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/salty-nonce-blinding-factor">extended KERI glossary</a>

[[def: schema, Schema]]

~ the [[ref: said]] of a JSON schema that is used to issue and verify an ACDC.  
~ Source: Dr. S.Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/schema">extended KERI glossary</a>

[[def: SCID, SCID, SCIDs]]

~ [[ref: self-certifying-identifier]]

[[def: secondary-root-of-trust, Secondary root-of-trust]]

~ In KERI its a [[ref: root-of-trust]] that, for its secure attribution, depends on another verifiable data structure (VDS) which MUST be a [[ref: primary-root-of-trust]].  
~ By its nature and cryptographic anchoring via [[ref: seal]] to a primary root-of-trust, a secondary root-of-trust still has a high level of trustability and can be automatically verified.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/secondary-root-of-trust">extended KERI glossary</a>

[[def: secure-asset-transfer-protocol, Secure asset-transfer protocol]]

~ An IETF protocol (and working group) in the making (as of mid 2022) for moving assets between blockchains.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/secure-asset-transfer-protocol">extended KERI glossary</a>

[[tref: toip1, secure-attribution, Secure Attribution]]

[[def: secure-private-authentic-confidentiality, Secure private authentic confidentiality, SPAC]]

~ ToIP Trust Spanning Layer Group realized we do have a secure authentication layer (KERI) but we don't have a secure confidentiality and privacy mechanism. Sam Smith proposes SPAC paper to define this.
~ Related:
~ https://www.usenix.org/system/files/sec22-cohen.pdf

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/secure-private-authentic-confidentiality">extended KERI glossary</a>

[[def: security-cost-performance-architecture-trade-off, Security cost performance architecture trade off]]

~ The degree of protection offered by a key management infrastructure usually forces a trade-off between security, cost, and performance.  
~ Typically, key generation happens relatively infrequently compared to event signing. But highly secure key generation may not support highly performant signing. This creates an architecture trade-off problem.  
~ Paraphrased from source [Universal Identifier Theory](https://github.com/SmithSamuelM/Papers/blob/master/whitepapers/IdentifierTheory_web.pdf) by Samuel Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/security-cost-performance-architecture-trade-off">extended KERI glossary</a>

[[def: security, Security, secure]]

~ 'secure' is free from or not exposed to danger or harm; safe. For [[ref: identifier]]s _security_ typically means secure from _exploit_ or _compromise_. More specifically an identifier is secure with respect to an entity if there is a mechanism by which that entity may prove it has [[ref: controller]] over the identifier. 

~ Also see TrustoverIP [[xref: toip1, security-policy, Security policy]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/security">extended KERI glossary</a>

[[def: selective-disclosure, Selective disclosure]]

~ a disclosure of an ACDC that selectively discloses its attributes using Compact Disclosure. The set of selectively disclosable attributes is provided as an array of blinded blocks where each attribute in the set has its own dedicated blinded block. Unlike Partial Disclosure, the selectively disclosed fields are not correlatable to the so far undisclosed but selectively disclosable fields in the same encompassing block.
~ Source: Dr. S. Smith  

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/selective-disclosure">extended KERI glossary</a>

[[def: self-addressed-data, Self-addressed data, SAD]]

~ a representation of data content from which a SAID is derived. The SAID is both cryptographically bound to (content-addressable) and encapsulated by (self-referential) its SAD [[ref: said]].  
~ Source: Dr. S.Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/self-addressed-data">extended KERI glossary</a>

[[def: self-addressing-data, Self-addressing data, SAD]]

~ an identifier that is content-addressable and self-referential. A SAID is uniquely and cryptographically bound to a serialization of data that includes the SAID as a component in that serialization [[ref: said]].  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/self-addressing-data">extended KERI glossary</a>

[[def: self-addressing-identifier, Self-addressing identifier, SAID]]

~ any identifier that is deterministically generated out of the content, or a digest of the content.  
~ Source: Dr. S. Smtih

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/self-addressing-identifier">extended KERI glossary</a>

[[def: self-certifying-identifier, self-certifying identifier, self-authenticating, self authenticating, SCID]]

~ a type of Cryptonym that is uniquely cryptographically derived from the public key of an asymmetric signing keypair (public, private).  
~ Source: Dr. S. Smith

~ Also see the TrustoverIP scope definition: [[xref: toip1, self-certifying-identifier, Self-certifying identifier]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/self-certifying-identifier">extended KERI glossary</a>

[[def: self-framing, Self-framing]]

~ a textual or binary encoding that begins with type, size, and value so that a parser knows how many characters (when textual) or bytes (when binary) to extract from the stream for a given element without parsing the rest of the characters or bytes in the element is Self-Framing. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/self-framing">extended KERI glossary</a>

[[tref: toip1, self-sovereign-identity, self-sovereign identity, SSI]]

[[def: semver, Semver, SEMVER]]

~ Semantic Versioning Specification 2.0. See also (https://semver.org)[https://semver.org]

[[def: server-sent-event, server-sent event]]

~ Mailbox notifications; a streaming service for the agent U/I, to get notifications from the KERI system itself.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/server-sent-event">extended KERI glossary</a>

[[tref: toip2, service-endpoint, Service Endpoint]]

~ In the KERI context it's an address where a given identifier can receive KERI [[ref: message]]s.

[[def: siger, Siger]]

~ [[ref: indexed-signature]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/siger">extended KERI glossary</a>

[[def: signature-verification-infrastructure, Signature Verification Infrastructure]]

~ An attack against signature verification infrastructure typically requires replacing the signature verification code with malicious code that falsely reports signature verification on signed statements. KERI provides a specific protection mechanism for signature verification via a Watcher pool where an event is only accepted as verified if a sufficient majority of the Watchers in a pool agree on the verification status of the signature(s) on that event. This provides a threshold structure where an attacker must compromise the code integrity of a sufficient number of Watchers for successful attack. Because the composition of a Watcher pool does not need to be publicly disclosed, an attacker must also discover that composition to ensure a successful attack.

[[def: signer, Signer]]

~ A primitive that represents a private key. It has the ability to create Sigers and Cigars (signatures).  
~ [Source](https://github.com/WebOfTrust/cesride#terminology) by Jason Colburne
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/signer">extended KERI glossary</a>

[[def: signify-keria-request-authentication-protocol, signify keria request authentication protocol, SKRAP]]

~ SKRAP is a client to the KERIA server. Mobile clients will be using SKRAP to connect to KERI [[ref: AID]]s via [[ref: agent]]s in the new, multi-tenant Mark II Agent server, [[ref: keria]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/signify-keria-request-authentication-protocol">extended KERI glossary</a>

[[def: signify, signify]]

~ Signify is a web client [[ref: key-event]] signing - and key pair creation app that minimizes the use of [[ref: KERI]] on the client.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/signify">extended KERI glossary</a>

[[def: signing-authority, signing authority]]

~ The authority to sign on behalf of the controller of the authoritative key pair. Often in situation where delegation has taken place, e.g. a custodial agent. These are limited rights because [[ref: rotation-authority]] is not included. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/signing-authority">extended KERI glossary</a>

[[def: simple-keri-for-web-auth, simple keri for web auth]]

~ A [[ref: KERI]] implementation that sacrifices performance or other non-security feature for usability. In general a narrow application of KERI may not require all the features of KERI but those features that it does support must still be secure.  
~ More on source [Github Repo SKWA](https://github.com/WebOfTrust/skwa).

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/simple-keri-for-web-auth">extended KERI glossary</a>

[[def: SKRAP]]

~ [[ref: signify-keria-request-authentication-protocol]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/SKRAP">extended KERI glossary</a>

[[def: SKWA]]

~ [[ref: simple-keri-for-web-auth]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/SKWA">extended KERI glossary</a>

[[def: sniffable, Sniffable]]

~ A stream is _sniffable_ as soon as it starts with a group code or field map; in fact this is how our parser ([[ref: parside]]) works. and detects if the CESR stream contains a certain datablock. 
~ The datablock of CESR binary, CESR Text, JSON, CBOR, MGPK have an Object code or the Group code (binary or text) and it's always a recognizable and unique _three bit combination_.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/sniffable">extended KERI glossary</a>

[[def: sniffer, sniffer]]

~ The _sniffer_ is part of [[ref: parside]] and detects if the CESR stream contains CESR binary, CESR Text, JSON, CBOR, MGPK. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/sniffer">extended KERI glossary</a>

[[def: solicited-issuance, Solicited issuance]]

~ The issuance of a Legal Entity vLEI Credentials, [[ref: OOR]] vLEI Credentials and [[ref: ECR]] vLEI Credentials upon receipt by the [[ref: QAR]] of a Fully Signed issuance request from the [[ref: AVR]](s) of the [[ref: legal-entity]].  
~ [Source](https://www.gleif.org/vlei/introducing-the-vlei-ecosystem-governance-framework/2022-02-07_verifiable-lei-vlei-ecosystem-governance-framework-glossary-draft-publication_v0.9-draft.pdf): Draft vLEI Ecosystem Governance Framework Glossary.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/solicited-issuance">extended KERI glossary</a>

[[def: SPAC]]

~ [[ref: secure-private-authentic-confidentiality]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/SPAC">extended KERI glossary</a>

[[def: spurn, Spurn]]

~ To _reject_. In KERI, "spurn" refers to a cryptographic or protocol-based act of rejecting an invalid or untrusted event. This rejection is deliberate and purposeful, ensuring the system's integrity by disregarding information that does not meet the necessary validation criteria. The verb 'spurn' is first used in the [[ref: IPEX]] specification.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/spurn">extended KERI glossary</a>

[[def: ssi-system, SSI system]]

~ The SSI Infrastructure consists of the technological components that are deployed all over the world for the purpose of providing, requesting and obtaining data for the purpose of negotiating and/or executing electronic [transactions](https://essif-lab.github.io/framework/docs/terms/transaction).
~ Paraphrased by @henkvancann based on source [eSSIF-lab](https://essif-lab.github.io/framework/docs/terms/ssi-infrastructure)

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/ssi-system">extended KERI glossary</a>

[[tref: toip1, SSI]]

[[def: stable, Stable]]

~ Refers to the state of cryptographic verifiability across a network or system. It generally implies that a particular identifier, event, or data set is consistent, fully verified, and cannot be contested within KERI.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/stable">extended KERI glossary</a>

[[def: stale-event, Stale event]]

~ A stale key event is an outdated or irrelevant (key) event involving an [[ref: stale-key]] that may compromise security.

~ See also: [[ref: stale-key]]

[[def: stale-key, stale key]]

~ A stale key is an outdated or expired encryption key that should no longer be used for securing data

~ See also: [[ref: stale-event]]

[[def: stream, Stream]]

~ a [[ref: CESR]] Stream is any set of concatenated Primitives, concatenated groups of Primitives, or hierarchically composed groups of [[ref: primitive]]s.  
~ Source: Dr. S. Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/stream">extended KERI glossary</a>

[[def: streamer, Streamer]]

~  A convenience class for supporting stream parsing, including nested (tunneled, encrypted) [[ref: CESR]] streams. Streams can be a mixture/combination of different [[ref: primitive]], including other streams. A stream is a concatenation of primitives.  
~ Source: Kent Bull in chat Zoom meeting KERI Aug 6, 2024.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/streamer">extended KERI glossary</a>

[[def: strip-parameter, Strip parameter]]

~ tells us what part of the [[ref: CESR]] stream will be parsed by which code.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/strip-parameter">extended KERI glossary</a>

[[def: targeted-acdc, Targeted acdc]]

~ an ACDC with the presence of the Issuee field in the attribute or attribute aggregate sections.  
~ Source: Dr. S.Smith

~ [[ref: untargeted-acdc]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/targeted-acdc">extended KERI glossary</a>

[[def: TEL]]

~ [[ref: transaction-event-log]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/TEL">extended KERI glossary</a>

[[def: text-binary-concatenation-composability, Text-binary-concatenation composability]]

~ An encoding has _composability_ when any set of [[ref: self-framing]] concatenated primitives expressed in either the text domain or binary domain may be converted as a group to the other domain and back again without loss.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/text-binary-concatenation-composability">extended KERI glossary</a>

[[def: tholder, Tholder]]

~ t-holder object that supports fractionally-weighted [[ref: signing-threshold]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/tholder">extended KERI glossary</a>

[[def: threshold-of-accountable-duplicity, Threshold of accountable duplicity, TOAD]]

~ The threshold of accountable duplicity (TOAD) is a threshold number `M` that the controller declares to accept accountability for an event when any subset `M` of the `N` witnesses confirm that event. The threshold `M` indicates the minimum number of confirming witnesses the controller deems sufficient given some number `F` of potentially faulty witnesses, given that `M >= N - F`. This enables a controller to provide itself with any degree of protection it deems necessary given this accountability.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/threshold-of-accountable-duplicity">extended KERI glossary</a>

[[def: threshold-signature-scheme, Threshold signature scheme]]

~ or TSS; is a type of digital signature protocol used by [Mutli-party Computation (MPC)](https://cryptoapis.io/products/wallet-as-a-service/mpc) wallets to authorize transactions or key state changes.  
~ Source [Cryptoapis](https://cryptoapis.io/blog/78-what-is-the-threshold-signature-scheme)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/threshold-signature-scheme">extended KERI glossary</a>

[[def: TOAD]]

~ [[ref: threshold-of-accountable-duplicity]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/TOAD">extended KERI glossary</a>

[[def: top-level-section, Top-level section]]

~ The fields of an ACDC in [[ref: compact-variant]]. The value of a top level section field is either the SAD or the SAID of the SAD of the associated section.
~ An Issuer commitment via a signature to any variant of ACDC (compact, full, etc) makes a cryptographic commitment to the top-level section fields shared by all variants of that ACDC.  
~ Paraphrased by @henkvancann based on [source](https://github.com/WebOfTrust/ietf-ipex/blob/main/draft-ssmith-ipex.md#example-most-compact-variant).

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/top-level-section">extended KERI glossary</a>

[[def: transaction-event-log, transaction event log, TEL]]

~ The set of transactions that determine registry state form a log called a Transaction Event Log (TEL). The TEL provides a cryptographic proof of registry state by reference to the corresponding controlling [[ref: key-event-log]]. Any validator may therefore cryptographically verify the [[ref: authoritative]] of the [[ref: registry]].

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/transaction-event-log">extended KERI glossary</a>

[[def: transfer-off-ledger, Transfer off-ledger]]

~ The act of transferring control authority over an identifier from a ledger (or blockchain) to the native verifiable KERI data structure Key Event Log.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/transfer-off-ledger">extended KERI glossary</a>

[[tref: toip1, transferable-identifier, Transferable identifier]]

[[tref: toip1, transferable, Transferable]]

[[def: trust-domain, Trust domain]]

~ A trust domain is the ecosystem of interactions that rely on a trust basis. A trust basis binds controllers, identifiers, and key-pairs. _For example the Facebook ecosystem of social interactions is a trust domain that relies on Facebook’s identity system of usernames and passwords as its trust basis._  
~ ([Source whitepaper](https://github.com/SmithSamuelM/Papers/blob/master/whitepapers/KERI_WP_2.x.web.pdf))

~ See also: [[xref: toip1, trust-domain]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/trust-domain">extended KERI glossary</a>

[[def: trust-spanning-protocol, trust spanning protocol]]

~ Protocol using [[ref: verifiable-identifier]]s that signs every single message on the internet and makes them verifiable.

~ Also see TrustoverIP [[xref: toip1, toip-trust-spanning-protocol, ToIP Trust Spanning Protocol]]

[[def: TSP, TSP, tsp]]

~ [[ref: trust-spanning-protocol]]

[[def: univalent, Univalent]]

~ In identifier systems, univalent means having a unique and non-ambiguous identifier for each entity or resource. This means that there is a *one-to-one correspondence* between the identifiers and the entities, and that no two different entities share the same identifier. 
~ Source: Bing chat, Sept 2023

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/univalent">extended KERI glossary</a>

[[def: unpermissioned-correlation, Unpermissioned correlation]]

~ a correlation established between two or more disclosed ACDCs whereby the discloser of the ACDCs does not permit the disclosee to establish such a correlation.  
~ Source: Dr. S. Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/unpermissioned-correlation">extended KERI glossary</a>

[[def: unsolicited-issuance, Unsolicited issuance]]

~ Issuance of a Legal Entity vLEI Credential upon notice by a [[ref: QAR]] to the [[ref: AVR]](s) of the Legal Entity that a Legal Entity vLEI Credential has been solicited on the [[ref: legal-entity]]’s behalf.  
~ [Source](https://www.gleif.org/vlei/introducing-the-vlei-ecosystem-governance-framework/2022-02-07_verifiable-lei-vlei-ecosystem-governance-framework-glossary-draft-publication_v0.9-draft.pdf): Draft vLEI Ecosystem Governance Framework Glossary.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/unsolicited-issuance">extended KERI glossary</a>

[[def: untargeted-acdc, Untargeted ACDC, Untargeted acdc]]

~ an ACDC without the presence of the Issuee field in the attribute or attribute aggregate sections.  
~ Source: Dr. S. Smith

~ [[ref: targeted-acdc]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/untargeted-acdc">extended KERI glossary</a>

[[def: vcp]]

~ vcp = vdr incept, verifiable data registry inception

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/vcp">extended KERI glossary</a>

[[def: VCTEL]]

~ [[ref: virtual-credential-transaction-event-log]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/VCTEL">extended KERI glossary</a>

[[def: vdr]]

~ [[ref: verifiable-data-registry]]
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/vdr">extended KERI glossary</a>

[[def: verfer]]

~ A primitive that represents a public key. It has the ability to [[ref: verify]] signatures on data.  
~ [Source](https://github.com/WebOfTrust/cesride#terminology) by Jason Colburne
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/verfer">extended KERI glossary</a>

[[def: verifiable-credential, Verifiable credential]]

~ Verifiable credentials (VCs) are an [open standard](https://en.wikipedia.org/wiki/Open_standard) for digital credentials. They can represent information found in physical credentials, such as a passport or license, as well as new things that have no physical equivalent, such as ownership of a bank account.

~ See also: [[xref: toip1, verifiable-credential, Verifiable credential]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/verifiable-credential">extended KERI glossary</a>

[[def: verifiable-data-registry, Verifiable data registry]]

~ A role a system might perform by mediating issuance and verification of ACDCs. See [verifiable data registry](https://www.w3.org/TR/vc-data-model-2.0/#dfn-verifiable-data-registries).

[[tref: toip1, verifiable-identifier, Verifiable identifier, VID]]

[[def: verifiable-legal-entity-identifier, Verifiable legal entity identifier]]

~ Verifiable credentials are issued by authorized validation agents ([[ref: QVI]]) under the governance of [[ref: GLEIF]], who delegate tasks to these agents. They provide cryptographic proof that the information about a legal entity, as linked to its Legal Entity Identifier (LEI), is verifiably authentic, accurate, and up-to-date.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/verifiable-legal-entity-identifier">extended KERI glossary</a>

[[def: verifiable, Verifiable]]

~ a condition of a KEL: being internally consistent with the integrity of its backward and forward chaining digest and authenticity of its non-repudiable signatures.  
~ Source: Dr. S. Smith

~ Explanation: 
~ Able to cryptographically verify a certain data structure on its [[ref: inconsistency]] and its [[ref: authenticity]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/verifiable">extended KERI glossary</a>

[[def: verification, Verification]]

~ An action an [[ref: agent]] (of a principal) performs to determine the [[ref: authenticity]] of a claim or other digital object using a cryptographic key.  
~ Source: ToIP glossary, Jan 2024.

~ See also [[xref: toip1, verification]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/verification">extended KERI glossary</a>

[[def: verifier, Verifier]]

~ An entity or component that cryptographically verifies the signature(s) on an event message.

~ See also: [[xref:toip1, verifier, Verifier]] in the main TrustoverIP glossary.

[[def: verify, Verify]]

~ The act, by or on behalf of a [[ref: party]], of determining whether that data is [[ref: authenticity]] (i.e. originates from the party that authored it), timely (i.e. has not expired), and conforms to other specifications that apply to its structure.  
~ [Source eSSIF-lab](https://essif-lab.github.io/framework/docs/essifLab-glossary#verify) in eSSIF-lab glossary

~ See also: [[xref: toip1, verification]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/verify">extended KERI glossary</a>

[[def: version-code, Version code]]

~ tells you which set of tables to load, it tells the table state. It's a unique code. what version of the table is going to load. 

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/version-code">extended KERI glossary</a>

[[def: version-string, Version string]]

~ the first field in any top-level KERI field map in which it appears.

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/version-string">extended KERI glossary</a>

[[def: version, Version]]

~ an instance of a KEL for an AID in which at least one event is unique between two instances of the [[ref: KEL]].  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/version">extended KERI glossary</a>

[[def: virtual-credential-transaction-event-log, Virtual credential transaction event log, VCTEL]]

~ will track the issued or revoked state of each virtual credential (VC) and will contain a reference to its corresponding _management transaction event log (management TEL)_.
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/virtual-credential-transaction-event-log">extended KERI glossary</a>

[[tref: vlei1, vlei, vLEI]]

[[def: vrt]]

~ vrt = vdr rotate, verifiable data registry rotation

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/vrt">extended KERI glossary</a>

[[def: watcher, Watcher]]

~ an _entity_ or _component_ that keeps a copy of a [[ref: kerl]] for an identifier but that is not designated by the _controller_ of the identifier as one of its witnesses. See annex [[ref: watcher]].  
~ Source: Dr. S.Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/watcher">extended KERI glossary</a>

[[def: weight-of-weights, Weight of weights]]

~ There are 2 levels in the multi-sign weighted thresholds of [[ref: multisig]] in [[ref: KERI]] because the solution only needs to focus on _tightly cooperating teams_.
~ - An individual using split keys over devices
~ - A team of teams

~ All other use cases can be solved by other means in KERI (e.g. [[ref: delegation]]).

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/weight-of-weights">extended KERI glossary</a>

[[def: weight, Weight]]

~ an optional field map in the Edge section that provides edge weight property that enables directed weighted edges and operators that use weights.  
~ Source: Dr. S.Smith
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/weight">extended KERI glossary</a>

[[def: well-known-witnesses, Well-known witnesses]]

~ Witness identifier creation by using _salts_ to initialize their key stores so that you can predict what identifiers will be created. For testing purposes only!

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/well-known-witnesses">extended KERI glossary</a>

[[def: witness, Witness]]

~ a witness is an entity or component designated (trusted) by the controller of an identifier. The primary role of a witness is to verify, sign, and keep events associated with an identifier. A witness is the controller of its own self-referential identifier which may or may not be the same as the identifier to which it is a witness. See also [[ref: keri’s-algorithm-for-witness-agreement]].  
~ Source: Dr. S. Smith

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/witness">extended KERI glossary</a>

[[def: xip]]

~ A XIP message allows a transaction set to be a mini peer to peer exchange to become a verifiable data structure. It makes the transaction become duplicity evident.

~ Source [KERI meeting 2024-03-12](https://wiki.trustoverip.org/pages/viewpage.action?pageId=80876836)
~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/xip">extended KERI glossary</a>

