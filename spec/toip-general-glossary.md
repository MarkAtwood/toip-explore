ToIP General Glossary 
==================

**Specification Status**: Public Review Draft 01 (PR1)

**Latest Draft:**

* [Github Repository](https://github.com/trustoverip/ctwg-general-glossary)
* [Submit/View Issues](https://github.com/trustoverip/ctwg-general-glossary/issues)
* [Discussions](https://github.com/trustoverip/ctwg-general-glossary/discussions)

**Editors:**

- [Drummond Reed](https://github.com/talltree), [Gen](https://www.gendigital.com)
- [Henk van Cann](https://github.com/henkvancann)

**Contributors:**
- [Kor Dwarshuis](https://github.com/kordwarshuis/)


**Participate:**

- [GitHub repo](https://github.com/trustoverip/ctwg-general-glossary)
- [Commit history](https://github.com/trustoverip/ctwg-general-glossary/commits/main)

------------------------------------

## Status

This is the first public review draft of the ToIP General Glossary. It is also the first version published using the [Spec-Up-T specification editing utility](https://github.com/trustoverip/spec-up-t)
based on [Spec-Up specification editing utility](https://identity.foundation/spec-up/) developed by the [Decentralized Identity Foundation](http://identity.foundation/).

## Copyright Notice

This specification is subject to the **OWF Contributor License Agreement 1.0 - Copyright**
available at
[https://www.openwebfoundation.org/the-agreements/the-owf-1-0-agreements-granted-claims/owf-contributor-license-agreement-1-0-copyright](https://www.openwebfoundation.org/the-agreements/the-owf-1-0-agreements-granted-claims/owf-contributor-license-agreement-1-0-copyright).

These terms are inherited from the [Technical Stack Working Group](https://wiki.trustoverip.org/display/HOME/Technology+Stack+Working+Group) at the Trust over IP (ToIP) Foundation. [Working Group Charter](https://trustoverip.org/wp-content/uploads/TSWG-2-Charter-Revision.pdf)


## Terms of Use

These materials are made available under and are subject to the [OWF CLA 1.0 - Copyright & Patent license](https://www.openwebfoundation.org/the-agreements/the-owf-1-0-agreements-granted-claims/owf-contributor-license-agreement-1-0-copyright-and-patent). Any source code is made available under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0.txt).

THESE MATERIALS ARE PROVIDED “AS IS.” The Trust Over IP Foundation, established as the Joint Development Foundation Projects, LLC, Trust Over IP Foundation Series ("ToIP"), and its members and contributors (each of ToIP, its members and contributors, a "ToIP Party") expressly disclaim any warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to the materials. The entire risk as to implementing or otherwise using the materials is assumed by the implementer and user.

IN NO EVENT WILL ANY ToIP PARTY BE LIABLE TO ANY OTHER PARTY FOR LOST PROFITS OR ANY FORM OF INDIRECT, SPECIAL, INCIDENTAL, OR CONSEQUENTIAL DAMAGES OF ANY CHARACTER FROM ANY CAUSES OF ACTION OF ANY KIND WITH RESPECT TO THESE MATERIALS, ANY DELIVERABLE OR THE ToIP GOVERNING AGREEMENT, WHETHER BASED ON BREACH OF CONTRACT, TORT (INCLUDING NEGLIGENCE), OR OTHERWISE, AND WHETHER OR NOT THE OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

## Introduction

The ToIP General Glossary is a deliverable of the ToIP Concepts and Terminology Working Group. Its purpose is to promote shared understanding of terms and concepts across the many different working groups, communities, enterprises, and ecosystems who are collaborating to develop and deploy decentralized digital trust infrastructure.

Contributions and feedback are encouraged from any stakeholder in this area of terminology.

## Linking to this Glossary

This glossary is designed to be both human and machine readable. All terms are listed alphabetically; acronyms are listed separately and linked to the fully expanded terms. Document authors can link directly to any term using standard web links and anchors following this syntax:

  `https://trustoverip.github.io/ctwg-general-glossary#term:xxxxx`

Where `xxxxx` is the term as it appears in the glossary, with any spaces are replaced by en-dashes (hyphens). For example, a link to the term `self-certifying identifer` would be:

  `https://trustoverip.github.io/ctwg-general-glossary#self-certifiying-identifier`

A specification document written using the [Trustoverip](https://trustoverip.org)'s open source [Spec-Up-T environment](https://trustoverip.github.io/spec-up-t/) documented in the [Spec-Up-T manual](https://trustoverip.github.io/spec-up-t-website/), originally based on [Decentralized Identity Foundation](http://identity.foundation/)'s open source [Spec-Up editor](https://identity.foundation/spec-up/).

The tool may create special external references to terms in this glossary using the Spec-Up `xref` and the `tref` tags following this syntax:

  `[ [xref: glossary, xxxxx] ]` and   `[ [tref: glossary, xxxxx] ]`
  
Note: we've put spaces between brackets to be able to present this literally; remove the spaces in use. 

  Where `glossary` is the text label the document author assigns to the URL of a Web-accessible glossary, and `xxxxx` is the term as it appears in that glossary, with any spaces are replaced by en-dashes (hyphens). For example, a Spec-Up external reference to the term `self-certifying identifer` using the label `toip` for this glossary would look like this:

  `[[xref: toip, self-certifying-identifier]]`

An item borrowed from an other glossary might look like this:

  `[[xref: keri, duplicity]]`

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
| PEMC IGR | Kantara Privacy Enhancing Mobile Credentials Implementors Guidance Report | https://kantarainitiative.org/download/pemc-implementors-guidance-report/ |
| W3C DID | W3C Decentralized Identifiers (DIDs) 1.0 | https://www.w3.org/TR/did-core/#terminology |
| W3C VC | W3C VC Data Model 1.1 | https://www.w3.org/TR/vc-data-model/#terminology |
| Ethereum | Ethereum.org Glossary | https://ethereum.org/ |
| Merriam-Webster | Merriam-Webster Dictionary | https://www.merriam-webster.com/dictionary/ |


## Terms and Definitions

<!-- Leave this code snippet if you want an alphabet index -->
<div id="alphabet-index-h7vc6omi2hr2880"></div>

- - -
<!-- End of code snippet for alphabet index -->
[[def: ADR, ADR]]

~ [[ref: architectural-decision-record]]

[[def: agency, agency]]

~ Agents can be people, edge computers and the functionality within [wallets](https://github.com/trustoverip/acdc/wiki/_new#digital-identity-wallet); the service an [[xref: toip1, agent]] offers.

[[def: API, API]]

~ [[ref: application-programming-interface]]

[[def: append-only-event-logs, append-only event logs]]

~ Append-only is a property of computer data storage such that new data can be appended to the storage, but where existing data is immutable.

~ A blockchain is an example of an append-only log. The events can be transactions. Bitcoin is a well-known Append only log where the events are _totally ordered_ and signed transfers of control over unspent transaction output.

~ More on [Wikipedia](https://en.wikipedia.org/wiki/Append-only)

[[def: application-programming-interface, application programming interface]]

~ An application programming interface (API) is a way for two or more [computer programs](https://en.wikipedia.org/wiki/Computer_program) to communicate with each other. It is a type of software [interface](https://en.wikipedia.org/wiki/Interface_(computing)), offering a service to other pieces of [software](https://en.wikipedia.org/wiki/Software). 

[[def: architectural-decision-record, architectural-decision record]]

~ Is a justified software design choice that addresses a functional or non-functional requirement that is architecturally significant.  
~ [Source adr.github.io](https://adr.github.io/)

[[def: authentic-web, authentic web]]

~ The authentic web is the internet as a whole giant verifiable data structure. Also called _Web5_. The web will be one big graph. That's the mental model of the 'authentic web'.

[[def: authenticity, authenticity]]

~ The quality of having an objectively verifiable origin ; contrast [[ref: veracity]]. When a newspaper publishes a story about an event, every faithful reproduction of that story may be *authentic* &mdash; but that does not mean the story was *true* (has *veracity*).

~ Authenticity is strongly related to digital [[ref: security]]. Ideally it should be [[ref: verifiable]] (to a [[ref: root-of-trust]]). The future picture therein is the [[ref: authentic-web]].

[[def: authority, authority]]

~ https://glossary.trustoverip.org/#term:authority

[[def: authorization, authorization]]

~ Is the function of specifying access rights/privileges to resources, which is related to general [information security](https://en.wikipedia.org/wiki/Information_security) and [computer security](https://en.wikipedia.org/wiki/Computer_security), and to [access control](https://en.wikipedia.org/wiki/Access_control) in particular.

~ More formally, "to authorize" is to define an access policy.

[[def: autonomic-computing-systems, autonomic computing systems]]

~ Self managing computing systems using algorithmic governance, from the 90's way way way before DAOs. KERI creator Sam Smith worked at funded Navy research in the 90's on autonomic survivable systems as in "self-healing" systems: "We called them autonomic way back then".

[[def: base64, base64]]

~ In [computer programming](https://en.wikipedia.org/wiki/Computer_programming), Base64 is a group of [binary-to-text encoding](https://en.wikipedia.org/wiki/Binary-to-text_encoding) schemes that represent [binary data](https://en.wikipedia.org/wiki/Binary_data) (more specifically, a sequence of 8-bit bytes) in sequences of 24 bits that can be represented by four 6-bit Base64 digits.

~ More on source [Wikipedia](https://en.wikipedia.org/wiki/Base64)

[[def: BFT, BFT]]

~ [[ref: byzantine-fault-tolerance]]

[[def: blake3, blake3]]

~ BLAKE3 is a relatively young (2020) cryptographic hash function based on Bao and BLAKE2.

[[def: branch, branch]]

~ In software development a 'branch' refers to the result of branching: the duplication of an object under version control for further separate modification.

[[def: byzantine-agreement, byzantine agreement]]

~ (non PoW) Byzantine Agreement is [[ref: byzantine-fault-tolerance]] of distributed computing systems that enable them to come to consensus despite arbitrary behavior from a fraction of the nodes in the network. BA consensus makes no assumptions about the behavior of nodes in the system. Practical Byzantine Fault Tolerance (pBFT) is the prototypical model for Byzantine agreement, and it can reach consensus fast and efficiently while concurrently decoupling consensus from resources (i.e., financial stake in PoS or electricity in PoW).

[[def: byzantine-fault-tolerance, byzantine-fault tolerance]]

~ A Byzantine fault (also interactive consistency, source congruency, error avalanche, [[ref: byzantine-agreement]] problem, Byzantine generals problem, and Byzantine failure) is a condition of a computer system, particularly distributed computing systems, where components may fail and there is imperfect information on whether a component has failed.

[[def: canonicalization, canonicalization]]

~ In computer science, canonicalization (sometimes standardization or [normalization](https://en.wikipedia.org/wiki/Normalization_(statistics))) is a process for converting data that has more than one possible representation into a "standard," "normal," or [canonical form](https://en.wikipedia.org/wiki/Canonical_form).  
~ This can be done to compare different representations for equivalence, to count the number of distinct data structures, to improve the efficiency of various algorithms by eliminating repeated calculations, or to make it possible to impose a meaningful sorting order.

~ More on source [Wikipedia](https://en.wikipedia.org/wiki/Canonicalization)

[[def: CBOR, CBOR]]

~ [[ref: concise-binary-object-representation]]

[[def: certificate-transparency, certificate transparency]]

~ Certificate Transparency (CT) is an Internet security standard and open source framework for monitoring and auditing digital certificates. The standard creates a system of public logs that seek to eventually record all certificates issued by publicly trusted certificate authorities, allowing efficient identification of mistakenly or maliciously issued certificates. As of 2021, Certificate Transparency is mandatory for all SSL/TLS certificates.

[[def: chain-of-custody, chain of custody]]

~ From Wikipedia ([Source](https://en.wikipedia.org/wiki/Chain_of_custody)):
~ Chain of custody (CoC), in legal contexts, is the chronological documentation or [paper trail](https://en.wiktionary.org/wiki/paper_trail) that records the sequence of custody, control, transfer, analysis, and disposition of materials, including physical or electronic [evidence](https://en.wikipedia.org/wiki/Evidence). Of particular importance in criminal cases, the concept is also applied in civil litigation and more broadly in drug testing of athletes and in [supply chain management](https://en.wikipedia.org/wiki/Supply_chain_management), e.g. to improve the [traceability](https://en.wikipedia.org/wiki/Traceability) of food products, or to provide assurances that wood products originate from [sustainably managed forests](https://en.wikipedia.org/wiki/Sustainable_forest_management).

[[def: Challenge Message, challenge-message]]

~ A message sent and responded to during an Identity Authentication session.

[[def: claim, claim]]

~ An assertion of the truth of something, typically one which is disputed or in doubt. A set of claims might convey personally identifying information: name, address, date of birth and citizenship, for example. ([Source](https://www.identityblog.com/?p=352)).

[[def: clone, clone]]

~ A copy of a system that is - and works exactly as the original

[[def: cloud-agent, cloud agent]]

~ Cloud agent is software that is installed on the cloud server instances in order to provide security, monitoring, and analysis solutions for the cloud. They actually provide information and helps to provide control over cloud entities.   
~ _Paraphrased by @henkvancann based on [source](https://www.cloudopedia.com/cloud-agent/)_.   
~ Also see [[ref: agent]].

[[def: code-table, code table]]

~ a code table is the Internet's most comprehensive yet simple resource for browsing and searching for [alt codes](https://www.codetable.net/altkeycodes), [ascii codes](https://www.codetable.net/asciikeycodes), [entities in html](https://www.codetable.net/entitiesinhtml), [unicode characters](https://www.codetable.net/unicodecharacters), and [unicode groups and categories](https://www.codetable.net/groups).   
~ [Source](https://www.codetable.net)

[[def: collision, collision]]

~ In cryptography and identity _collision_ generally refers to something going wrong because an identical result has been produced but it refers to - or points to - different sources or assets backing this result.

~ E.g. two hashes collide, meaning two different digital sources produce the same hash.  
~ Another example is [name(space) collision](https://en.wikipedia.org/wiki/Naming_collision).

[[def: complementary-integrity-verification, complementary integrity verification]]

~ A mechanism that can verify integrity independent of needing access to a previous instance or reference version of the information for comparison.  
~ Source: Neil Thomson

[[def: concatenation, concatenation]]

~ In [formal language theory](https://en.wikipedia.org/wiki/Formal_language) and [computer programming](https://en.wikipedia.org/wiki/Computer_programming), string concatenation is the operation of joining [character strings](https://en.wikipedia.org/wiki/Character_string_(computer_science)) [end-to-end](https://en.wiktionary.org/wiki/end-to-end). For example, the concatenation of "snow" and "ball" is "snowball".  
~ More on source [Wikipedia page](https://en.wikipedia.org/wiki/Concatenation)

[[def: concise-binary-object-representation]]

~ It is a binary data [serialization](https://en.wikipedia.org/wiki/Serialization) format loosely based on [JSON](https://en.wikipedia.org/wiki/JSON) authored by C. Bormann. Like JSON it allows the transmission of data objects that contain [name–value pairs](https://en.wikipedia.org/wiki/Attribute%E2%80%93value_pair), but in a more concise manner. This increases processing and transfer speeds at the cost of [human readability](https://en.wikipedia.org/wiki/Human-readable_medium).

~ Also knows as: [[ref: CBOR]]

[[def: confidentiality, confidentiality]]

~ All statements in a conversation are only known by the parties to that conversation.  
~ Source: Samuel Smith, at IIW-37, Oct 2023.

[[def: configuration-files, configuration files]]

~ In [computing](https://en.wikipedia.org/wiki/Computing), configuration files (commonly known simply as config files) are [files](https://en.wikipedia.org/wiki/Computer_file) used to configure the [parameters](https://en.wikipedia.org/wiki/Parameter_(computer_programming)) and [initial settings](https://en.wikipedia.org/wiki/Initialization_(programming)) for some [computer programs](https://en.wikipedia.org/wiki/Computer_program). They are used for user [applications](https://en.wikipedia.org/wiki/Application_software), [server processes](https://en.wikipedia.org/wiki/Server_(computing)) and [operating system](https://en.wikipedia.org/wiki/Operating_system) settings.

~ More on source [Wikipedia](https://en.wikipedia.org/wiki/Configuration_file)

[[def: consensus-mechanism, consensus mechanism]]

~ How groups of entitities come to decisions. In general to learn about consensus mechanisms read any textbook on decision making, automated reasoning, multi-objective decision making, operations research etc.

[[def: content-addressable-hash, content-addressable hash]]

~ Finding content by a hash of this content, generated by a one-way hash function applied to the content.

~ Content addressing is a way to find data in a network using its content rather than its location. The way we do is by taking the content of the content and hashing it. Try uploading an image to IPFS and get the hash using the below button. 

[[def: coroutines, coroutines]]

~ Computer programs that can be suspended and resumed at will.

[[def: CRUD, CRUD]]

~ Is acronym for the traditional _client-server_ database update policy is CRUD (**Create, Read, Update, Delete**). 

~ CRUD as opposed to [[ref: RUN]] which is the acronym for the new peer-to-peer end-verifiable monotonic update policy.

[[def: crypto-libraries, crypto libraries]]

~ Cryptography libraries deal with cryptography algorithms and have API function calls to each of the supported features. 

[[def: cryptocurrency, cryptocurrency]]

~ A digital asset designed to work as a medium of exchange wherein individual coin ownership records are stored in a digital ledger or computerized database using strong cryptography to secure transaction record entries, to control the creation of additional digital coin records.  
~ See [more](https://en.wikipedia.org/wiki/Cryptocurrency) on source Wikipedia.

[[def: cryptographic-commitment-scheme, cryptographic commitment scheme]]

~ is a cryptographic primitive that allows one to commit to a chosen value (or chosen statement) while keeping it hidden to others, with the ability to reveal the committed value later. 

~ Commitment schemes are designed so that a party cannot change the value or statement after they have committed to it: that is, commitment schemes are _binding_.  
~ More on [wikipedia](https://en.wikipedia.org/wiki/Commitment_scheme)

[[def: cryptographic-primitive, Cryptographic Primitive]]

~ the serialization of a value associated with a cryptographic operation including but not limited to a digest (hash), a salt, a seed, a private key, a public key, or a signature.  
~ Source: Dr. S.Smith, 2024

[[def: cryptographic-strength, cryptographic strength]]

~ The term "cryptographically strong" is often used to describe an encryption algorithm, and implies, in comparison to some other algorithm (which is thus cryptographically weak), greater resistance to attack. But it can also be used to describe hashing and unique identifier and filename creation algorithms.  
~ More on [Wikipedia](https://en.wikipedia.org/wiki/Strong_cryptography)

[[def: cryptonym, cryptonym]]

~ a cryptographic pseudonymous identifier represented by a string of characters derived from a random or pseudo-random secret seed or salt via a one-way cryptographic function with a sufficiently high degree of cryptographic strength (e.g., 128 bits, see appendix on [[ref: cryptographic-strength]]. A cryptonym is a type of [[ref: primitive]]. 

[[def: CSPRNG, CSPRNG]]

~ means "Cryptographically Secure Pseudorandom Number Generator," which means that a sequence of numbers (bits, bytes...) that is produced from an algorithm that is deterministic (the sequence is generated from some unknown internal state), hence pseudorandom is also cryptographically secure, or not.  
~ (Source: https://crypto.stackexchange.com/questions/12436/what-is-the-difference-between-csprng-and-prng)

[[def: CT, CT]]

~ [[ref: certificate-transparency]]

[[def: DAG, DAG]]

~ [[ref: directed-acyclic-graph]]

[[def: data-anchor, data anchor]]

~ Data anchors are [[ref: digest]] of digital data, that uniquely identify this data. The digest is the anchor and can be used to identify - and point to the data at the same time. 

[[def: decentralized-identifier, decentralized identifier]]

~ Decentralized identifiers (DID) are a new type of identifier that enables verifiable, decentralized digital identity. A _DID_ refers to any subject (e.g., a person, organization, thing, data model, abstract entity, etc.) as determined by the controller of the DID.  
~ [Source](https://www.w3.org/TR/did-core/) W3C.org.

~ More technical notion: [[xref: toip1, decentralized-identifier, decentralized identifier]]

~ As known as: [[ref: DID]]

[[def: decentralized-identity, decentralized identity]]

~ is a technology that uses cryptography to allow individuals to create and control their own unique identifiers. They can use these identifiers to obtain `Verifiable Credentials` from trusted organizations and, subsequently, present elements of these credentials as proof of claims about themselves. In this model, the individual takes ownership of their own identity and does not need to cede control to centralized service providers or companies.

~ TrustoverIP related [[xref: toip1, decentralized-identity, decentralized identity]]

~ KERI related [[xref: keri1, decentralized-identity, decentralized identity]]

[[def: decentralized-key-management-infrastructure, decentralized key-management infrastructure]]

~ a key management infrastructure that does not rely on a single entity for the integrity and security of the system as a whole. Trust in a DKMI is decentralized through the use of technologies that make it possible for geographically and politically disparate entities to reach an agreement on the key state of an identifier [DPKI](https://trustoverip.github.io/kswg-keri-specification/#term:dpki).  
~ Source: Dr. S.Smith, 2024

[[def: DHT, DHT]]

~ [[ref: distributed-hash-table]]

[[def: DID, DIDs]]

~ [[ref: decentralized-identifier]]

[[def: digest, digest]]

~ verifiable cryptographic commitment. It's a collision-resistant hash of content.

[[def: digital-signature, digital signature]]

~ A _digital_ signature is a mathematical scheme for verifying the authenticity of digital messages or documents. A valid digital signature, where the prerequisites are satisfied, gives a recipient very strong reason to believe that the message was created by a known sender (authentication), and that the message was not altered in transit (integrity).

[[def: directed-acyclic-graph, directed acyclic graph]]

~ From Wikipedia ([source](https://en.wikipedia.org/wiki/Directed_acyclic_graph)):

~ In [mathematics](https://en.wikipedia.org/wiki/Mathematics), particularly [graph theory](https://en.wikipedia.org/wiki/Graph_theory), and [computer science](https://en.wikipedia.org/wiki/Computer_science), a directed acyclic graph (DAG [/ˈdæɡ/](https://en.wikipedia.org/wiki/Help:IPA/English) ([listen](https://upload.wikimedia.org/wikipedia/commons/5/5a/En-us-DAG.ogg))) is a [directed graph](https://en.wikipedia.org/wiki/Directed_graph) with no [directed cycles](https://en.wikipedia.org/wiki/Cycle_graph#Directed_cycle_graph). That is, it consists of [vertices](https://en.wikipedia.org/wiki/Vertex_(graph_theory)) and [edges](https://en.wikipedia.org/wiki/Edge_(graph_theory)) (also called arcs), with each edge directed from one vertex to another.

~ <img src="https://hackmd.io/_uploads/rywIzRLo5.png" width="219" height="300" alt="A directed acyclic graph (DAG)"/>

[[def: distributed-hash-table, distributed hash table]]

~ It is a distributed system that provides a lookup service similar to a hash table: key-value pairs are stored in a DHT, and any participating node can efficiently retrieve the value associated with a given key. The main advantage of a DHT is that nodes can be added or removed with minimum work around re-distributing keys.

[[def: DKMI, DKPI, dkmi, dkpi]]

~ [[ref: decentralized-key-management-infrastructure]]

~ More in <a href="https://weboftrust.github.io/WOT-terms/docs/glossary/DKMI">extended KERI glossary</a>

[[def: domain-name, domain name]]

~ A domain name is a [string](https://en.wikipedia.org/wiki/String_(computer_science)) that identifies a realm of administrative autonomy, authority or control within the [Internet](https://en.wikipedia.org/wiki/Internet). Domain names are used in various networking contexts and for application-specific naming and addressing purposes.  
~ More on [Source Wikipedia](https://en.wikipedia.org/wiki/Domain_name).

[[def: double-spend-proof, double-spend proof]]

~ Total global ordering of transactions so that value can’t be spent twice at the same time from the unit of value. Or in everyday language: you can't spend your money twice. 

[[def: E2E, E2E]]

~ [[ref: end-to-end]]

[[def: eclipse-attack, eclipse attack]]

~ An eclipse attack is a [[ref: peer-to-peer]] network-based attack. Eclipse attack can only be performed on nodes that accept incoming connections from other nodes, and not all nodes accept incoming connections.

~ In a bitcoin network, by default, there are a maximum of 117 incoming TCP connections and 8 outgoing TCP connections.  
~ [Source](https://www.geeksforgeeks.org/what-is-an-eclipse-attack/)

[[def: electronic-signature, electronic signature]]

~ An electronic signature, or e-signature, refers to data in electronic form, which is logically associated with other data in electronic form and which is used by the signatory to sign. This type of signature has the same legal standing as a handwritten signature as long as it adheres to the requirements of the specific regulation under which it was created (e.g., eIDAS in the European Union, NIST-DSS in the USA or ZertES in Switzerland).

[[def: end-to-end, end to end]]

~ Inter-host communication and data flow transformations, considered in motion and at rest.
~ 1.	E2E Security.  Inter-host communication must be end-to-end signed/encrypted and data must be stored signed/encrypted. Data is signed/encrypted in motion and at rest.  
~ 2.	E2E Provenance.  Data flow transformations must be end-to-end provenanced using verifiable data items (verifiable data chains or VCs). Every change shall be provenanced.

~ Paraphrased from source [Universal Identifier Theory](https://github.com/SmithSamuelM/Papers/blob/master/whitepapers/IdentifierTheory_web.pdf) by Samuel Smith

[[def: entity, entity]]

~ [entity](https://trustoverip.github.io/essiflab/glossary#entity) in the **#essiflab** glossary.

[[def: entropy, entropy]]

~ Unpredictable information. Often used as a _secret_ or as input to a _key_ generation algorithm. 

[[def: ephemeral, ephemeral]]

~ Lasting for a markedly brief time. Having a short lifespan.  
~ In the context of identifiers is often referred to as identifiers for one time use; or throw-away identifiers.

[[def: escrow, escrow]]

~ 'Escrow' **as a noun** is a (legal) arrangement in which a third party temporarily holds money or property until a particular condition has been met.

~ 'Escrow' **as a verb**: we use it in protocol design to handle out of order events.  Store the event and wait for the other stuff to show up and then continue processing of the event. So _escrowing_ is the process of storing this event. We root back to the event later. 

[[def: extensible-business-reporting-language, extensible business reporting language]]

~ XBRL is the open international standard for digital business reporting, managed by a global not for profit consortium, XBRL International. 

[[def: FFI, FFI]]

~ [[ref: foreign-function-interface]]

[[def: foreign-function-interface, foreign function interface]]

~ Is a mechanism by which a program written in one, usually an [interpreted](https://en.wikipedia.org/wiki/Interpreted_(programming_languages)) (scripted), [programming language](https://en.wikipedia.org/wiki/Programming_language) that can call routines or make use of services written or compiled in another one.  
~ More on Source: https://en.wikipedia.org/wiki/Foreign_function_interface

[[def: GLEIF, GLEIF]]

~ Global Legal Entity Identifier Foundation

[[def: gnu-privacy-guard, gnu privacy guard]]

~ also GnuPG; is a free-software replacement for Symantec's PGP cryptographic software suite. It is compliant with RFC 4880, the IETF standards-track specification of OpenPGP. Modern versions of PGP are interoperable with GnuPG and other OpenPGP-compliant systems.  
~ More on [wikipedia](https://en.wikipedia.org/wiki/GNU_Privacy_Guard)  
~ See more about the closely related and often-confusing term [[ref: PGP]].

[[def: governance-framework, governance framework]]

~ Also called 'Governance structure'. Governance frameworks are the structure of a government and reflect the interrelated relationships, factors, and other influences upon the institution. Governance frameworks structure and delineate power and the governing or [management](https://en.wikipedia.org/wiki/Management) roles in an organization. They also set rules, procedures, and other informational guidelines.  
~ More in [source](https://en.wikipedia.org/wiki/Governance_framework) Wikipedia.

[[def: GPG, GPG]]

~ [[ref: gnu-privacy-guard]]

[[def: hardware-security-module, hardware security module]]

~ A HSM is a physical computing device that safeguards and manages secrets (most importantly [digital keys](https://en.wikipedia.org/wiki/Digital_keys)), performs [encryption](https://en.wikipedia.org/wiki/Encryption) and decryption functions for [digital signatures](https://en.wikipedia.org/wiki/Digital_signature), strong [[ref: authenticity]] and other cryptographic functions.  
~ More in source [Wikipedia](https://en.wikipedia.org/wiki/Hardware_security_module)

[[def: hierarchical-asynchronous-coroutines-and-input-output, hierarchical asynchronous coroutines and input output]]

~ HIO is an acronym which stands for 'Weightless hierarchical asynchronous coroutines and I/O in Python'.

~ It's Rich Flow Based Programming Hierarchical Structured Concurrency with Asynchronous IO. That mouthful of terms has been explained further on [Github](https://github.com/ioflo/hio).

~ HIO builds on very early work on hierarchical structured concurrency with lifecycle contexts from [ioflo](https://ioflo.com/), [ioflo github](https://github.com/ioflo/ioflo), and [ioflo manuals](https://github.com/ioflo/ioflo_manuals).

[[def: hierchical-deterministic-keys, hierchical deterministic keys]]

~ An HDK type is a deterministic Bitcoin wallet derived from a known [[ref: seed]] that allows child keys to be created from the parent key. Because the child key is generated from a known seed, a relationship between the child and parent keys is invisible to anyone without that seed.

[[def: hio, hio]]

~ Weightless hierarchical asynchronous coroutines and I/O in Python.  
~ Rich Flow Based Programming Hierarchical Structured Concurrency with Asynchronous IO.

[[def: HSM, HSM]]

~ [[ref: hardware-security-module]]

[[def: I-O, I O]]

~ [[ref: input-output]]

[[def: IANA, IANA]]

~ [[ref: internet-assigned-numbers-authority]]

[[def: identifier-system, identifier system]]

~ a system for uniquely identifying (public) identities

[[def: identifier, identifier]]

~ Something to uniquely identify (public) identities; pointing to something or someone else.

[[def: identity, identity]]

~ A unique entity. Typically represented by a unique [[ref: identifier]].

[[def: inconsistency, inconsistency]]

~ If a reason, idea, opinion, etc. is inconsistent, different parts of it do not agree, or it does not agree with something else. Data inconsistency occurs when similar data is kept in different formats in more than one file. When this happens, it is important to match the data between files.

[[def: input-output, input output]]

~ In [computing](https://en.wikipedia.org/wiki/Computing), input/output (I/O, or informally io or IO) is the communication between an information processing system, such as a [computer](https://en.wikipedia.org/wiki/Computer), and the outside world, possibly a human or another information processing system. [Inputs](https://en.wikipedia.org/wiki/Information) are the signals or [data](https://en.wikipedia.org/wiki/Data_(computing)) received by the system and outputs are the signals or data sent from it. The term can also be used as part of an action; to "perform I/O" is to perform an [input or output operation](https://en.wikipedia.org/wiki/I/O_scheduling).

[[def: integrity]]

~ Integrity (of a message or data) means that the information is whole, sound, and unimpaired (not necessarily correct). It means nothing is missing from the information; it is complete and in intended good order.  
~ Source: Neil Thomson

[[def: internal-inconsistency, internal inconsistency]]

~ Internal is used to describe things that exist or happen inside an [[ref: entity]]. In our scope of digital [[ref: identifier]] its (in)consistency is considered within the defining data structures and related data stores.

~ In [[ref: key-event-receipt-infrastructure]], you are protected against internal inconsistency by the hash chain data structure of the [[ref: key-event-log]] because the only [[ref: authority]] that can sign the log is the [[ref: controller]] itself.

[[def: internet-assigned-numbers-authority, internet assigned numbers authority]]

~ is the organization that oversees the allocation of [IP](https://www.techtarget.com/searchunifiedcommunications/definition/Internet-Protocol) addresses to internet service providers ([ISPs](https://www.techtarget.com/whatis/definition/ISP)).  
~ [Source](https://www.techtarget.com/whatis/definition/IANA-Internet-Assigned-Numbers-Authority)

[[def: interoperability, interoperability]]

~ Interoperability is a characteristic of a product or system to work with other products or systems. While the term was initially defined for [information technology](https://en.wikipedia.org/wiki/Information_technology) or [systems engineering](https://en.wikipedia.org/wiki/Systems_engineering) services to allow for information exchange.  
~ [More on source Wikipedia](https://en.wikipedia.org/wiki/Interoperability)

[[def: interoperable, interoperable]]

~ [[ref: interoperability]]

[[def:interplanetary-file-system, Interplanetary Filesystem, IPFS]]

~ The InterPlanetary File System (IPFS) is a protocol, hypermedia and file sharing peer-to-peer network for sharing data using a distributed hash table to store provider information.

~ Source [wikipedia](https://en.wikipedia.org/wiki/InterPlanetary_File_System)

[[def: ip-address, ip address]]

~ An Internet Protocol address (IP address) is a numerical label such as '192.0.2.1' that is connected to a [computer network](https://en.wikipedia.org/wiki/Computer_network) that uses the [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol) for communication. An IP address serves two main functions: network interface [identification](https://en.wikipedia.org/wiki/Identification_(information)) and location [addressing](https://en.wikipedia.org/wiki/Network_address).

~ Much more on source [Wikipedia](https://en.wikipedia.org/wiki/IP_address)

[[def: javascript-object-notation, javascript object notation]]

~ JSON (JavaScript Object Notation, pronounced [/ˈdʒeɪsən/](https://en.wikipedia.org/wiki/Help:IPA/English); also [/ˈdʒeɪˌsɒn/](https://en.wikipedia.org/wiki/Help:IPA/English)) is an [open standard](https://en.wikipedia.org/wiki/Open_standard) [file format](https://en.wikipedia.org/wiki/File_format) and [data interchange](https://en.wikipedia.org/wiki/Electronic_data_interchange) format that uses [human-readable](https://en.wikipedia.org/wiki/Human-readable_medium) text to store and transmit data objects consisting of [attribute–value pairs](https://en.wikipedia.org/wiki/Attribute%E2%80%93value_pair) and [arrays](https://en.wikipedia.org/wiki/Array_data_type) (or other [serializable](https://en.wikipedia.org/wiki/Serialization) values). It is a common data format with diverse uses in [electronic data interchange](https://en.wikipedia.org/wiki/Electronic_data_interchange), including that of [web applications](https://en.wikipedia.org/wiki/Web_application) with [servers](https://en.wikipedia.org/wiki/Server_(computing)).

[[def: javascript-object-signing-and-encryption, javascript object signing and encryption]]

~ is a framework intended to provide a method to securely transfer claims (such as authorization information) between parties. The JOSE framework provides a collection of specifications to serve this purpose. 

[[def: JOSE, JOSE]]

~ [[ref: javascript-object-signing-and-encryption]]

[[def: JSON, JSON]]

~ [[ref: javascript-object-notation]]

[[def: JSONPath]]

~ In computer software, JSONPath is a query language for querying values in JSON.

~ See more: [Wikipedia JSONPath](https://en.wikipedia.org/wiki/JSONPath)

[[def: key-compromise, key compromise]]

~ Basically there are three infrastructures that are included in “key management” systems that must be protected:
~ - Key pair creation and storage
~ - Event signing
~ - Event signature verification
~ So when we say “key compromise” we really mean compromise of one of those three things.

[[def: key-management, key management]]

~ Management of cryptographic keys in a crypto-system. This includes dealing with the generation, exchange, storage, use, crypto-shredding (destruction) and replacement of keys (also key-[[ref: rotation]]). It includes cryptographic protocol design, key servers, user procedures, and other relevant protocols.

[[def: key-pair, key pair, keypair]]

~ is an ordered pair consisting of a public key and its corresponding private key.

~ More: is a private key and its corresponding public key resulting from a one-way crypto-graphical function; a key pair is used with an asymmetric-key (public-key) algorithm in a so called [[ref: public-key-infrastructure]] (PKI).

[[def: key-state, key state]]

~ a set of currently authoritative keypairs for an AID and any other information necessary to secure or establish control authority over an AID. This includes current keys, prior next key digests, current thresholds, prior next thresholds, witnesses, witness thresholds, and configurations. 

[[def: key-store, key store]]

~ The on-device storage of public/private key pairs associated with an AID.

[[def: key-stretching, key stretching]]

~ In [cryptography](https://en.wikipedia.org/wiki/Cryptography), key stretching techniques are used to make a possibly weak [key](https://en.wikipedia.org/wiki/Key_(cryptography)), typically a [password](https://en.wikipedia.org/wiki/Password) or [passphrase](https://en.wikipedia.org/wiki/Passphrase), more secure against a [brute-force attack](https://en.wikipedia.org/wiki/Brute-force_attack) by increasing the resources (time and possibly space) it takes to test each possible key. 

[[def: key-transparency, key transparency]]

~ provides a lookup service for generic records and a public, tamper-proof audit log of all record changes. While being publicly auditable, individual records are only revealed in response to queries for specific IDs.

[[def: key, key]]

~ In our digital scope it's a mechanism for granting or restricting access to something. MAY be used to issue and prove, MAY be used to transfer and control over _identity_ and _cryptocurrency_. [More](https://en.wikipedia.org/wiki/Key_(cryptography))

[[def: keypair]]

~ [[ref:key-pair]]

[[def: keystore, keystore]]

~ A keystore in KERI is the encrypted data store that hold the private keys for a collection of AIDs.  
~ Source: Philip Feairheller.

[[def: large-language-model, large language model]]

~ A large language model (LLM) is a [language model](https://en.wikipedia.org/wiki/Language_model) consisting of a [neural network](https://en.wikipedia.org/wiki/Artificial_neural_network) with many parameters (typically billions of weights or more), trained on large quantities of unlabeled text using [self-supervised learning](https://en.wikipedia.org/wiki/Self-supervised_learning) or [semi-supervised learning](https://en.wikipedia.org/wiki/Semi-supervised_learning).  
~ More on [Source Wikipedia](https://en.wikipedia.org/wiki/Large_language_model)

[[def: lead-bytes, lead bytes]]

~ In order to avoid confusion with the use of the term [[ref: pad]] character, when [[ref: pre-pad]]ding with bytes that are not replaced later, we use the term **lead bytes**. So lead-bytes are added "pre-conversion".

[[def: legal-entity, legal entity]]

~ Unique parties that are legally or financially responsible for the performance of financial transactions or have the legal right in their jurisdiction to enter independently into legal contracts.

[[def: LEI, LEI]]

~ Legal Entity Identifier

[[def: levels-of-assurance, levels of assurance]]

~ Identity and other trust decisions are often not binary. They are judgement calls. Any time that judgement is not a simple “Yes/No” answer, you have the option for levels of assurance. Also 'LoA'.

[[def: liveness, liveness]]

~ Liveness refers to a set of properties of concurrent systems, that require a system to make progress despite the fact that its concurrently executing components ("processes") may have to "take turns" in critical sections, parts of the program that cannot be simultaneously run by multiple processes.

[[def: LLM, LLM]]

~ [[ref: large-language-model]]

[[def: LoA, LoA]]

~ [[ref: levels-of-assurance]]

[[def: LoC, LoC]]

~ [[ref: loci-of-control]]

[[def: loci-of-control, loci of control]]

~ Locus of control is the degree to which people believe that they, as opposed to external forces (beyond their influence), have control over the outcome of events in their lives. Also 'LoC'.   
~ More on [wikipedia](https://en.wikipedia.org/wiki/Locus_of_control)

[[def: media-type, media type]]

~ A Media type (formerly known as _MIME type_) is a standard way to indicate the nature and format of a file, in the same way as 'image/jpeg' for JPEG images, used on the internet.

~ It is a two-part identifier for file formats and format contents transmitted on the internet. Their purpose is somewhat similar to file extensions in that they identify the intended data format.

[[def: messagepack, messagepack]]

~ MessagePack is a [computer](https://en.wikipedia.org/wiki/Computer) data interchange format. It is a binary form for representing simple [data structures](https://en.wikipedia.org/wiki/Data_structure) like [arrays](https://en.wikipedia.org/wiki/Array_data_structure) and [associative arrays](https://en.wikipedia.org/wiki/Associative_array). MessagePack aims to be as compact and simple as possible. The official implementation is available in a variety of languages

[[def: MFA, MFA]]

~ [[ref: multi-factor-authentication]]

[[def: MIME-type, MIME type]]

~ [[ref: media-type]]

[[def: multi-factor-authentication, multi-factor authentication]]

~ Authentication by combining multiple security factors. Well-known factors are *what you know*, *what you have* and *what you are*. 

[[def: multicodec, multicodec]]

~ Is a self-describing multi-format, it wraps other formats with a tiny bit of self-description. A multi-codec identifier is both a variant (variable length integer) and the code identifying data. 

~ See more at [GitHub Multi-codec](https://github.com/multiformats/multicodec)

[[def: multiplexing, multiplexing]]

~ In [telecommunications](https://en.wikipedia.org/wiki/Telecommunications) and [computer networking](https://en.wikipedia.org/wiki/Computer_network), multiplexing (sometimes contracted to _muxing_) is a method by which multiple analog or digital signals are combined into one signal over a [shared medium](https://en.wikipedia.org/wiki/Shared_medium). The aim is to share a scarce resource - a physical [transmission medium](https://en.wikipedia.org/wiki/Transmission_medium).  
~ More on source [Wikipedia-page](https://en.wikipedia.org/wiki/Multiplexing)

[[def: multisig, multisig]]

~ also multi-signature or multisignature; is a [digital signature](https://en.wikipedia.org/wiki/Digital_signature) scheme which allows a group of users to sign a single piece of digital data.  
~ Paraphrased by @henkvancann from Wikipedia [source](https://en.wikipedia.org/wiki/Multisignature)

[[def: namespace, namespace]]

~ In an identity system, an identifier can be generalized to a _namespace_ to provide a systematic way of organizing identifiers for related resources and their attributes. A namespace is a grouping of symbols or identifiers for a set of related objects. 

[[def: NFT, NFT]]

~ [[ref: non-fungible-token]]

[[def: non-disclosure-agreement, Non-Disclosure Agreement, NDA]]

~ An agreement that outlines requirements for handling confidential information

[[def: non-fungible-token, non-fungible token]]

~ A non-fungible token (NFT) is a [financial security](https://en.wikipedia.org/wiki/Security_(finance)) consisting of digital data stored in a [blockchain](https://en.wikipedia.org/wiki/Blockchain), a form of [distributed ledger](https://en.wikipedia.org/wiki/Distributed_ledger). 

[[def: non-normative, non normative]]

~ A theory is called non-normative if it does not do what has described under '[[ref: normative]]'. In general, the purpose of non-normative theories is not to give answers, but rather to describe possibilities or predict what might happen as a result of certain actions.  
~ [Source](https://www.quora.com/What-is-the-difference-between-normative-and-non-normative?share=1).

[[def: normative, normative]]

~ a theory is “normative” if it, in some sense, tells you what you should do - what action you should take. If it includes a usable procedure for determining the optimal action in a given scenario.  
~ [Source](https://www.quora.com/What-is-the-difference-between-normative-and-non-normative?share=1).

[[def: one-way-function, one-way function]]

~ In computer science, a one-way function is a function that is easy to compute on every input, but hard to invert given the image of a random input. Here, "easy" and "hard" are to be understood in the sense of computational complexity theory, specifically the theory of polynomial time problems.  
~ More on [Wikipedia](https://en.wikipedia.org/wiki/One-way_function)

[[def: owner, owner]]

~ [Owner](https://github.com/trustoverip/toip/wiki/owner) in ToIP glossary

[[def: ownership, ownership]]

~ [Ownership](https://github.com/trustoverip/toip/wiki/ownership) in ToIP glossary

[[def: P2P, P2P]]

~ [[ref: peer-to-peer]]

[[def: pad, pad]]

~ is a [character](https://www.webopedia.com/definitions/character/) used to fill empty space, because many [applications](https://www.webopedia.com/definitions/application-software/) have [fields](https://www.webopedia.com/definitions/field/) that must be a particular length.  
~ [Source](https://www.webopedia.com/definitions/pad-character/)

[[def: passcode, passcode]]

~ A password, sometimes called a passcode (for example in [Apple](https://en.wikipedia.org/wiki/Apple_Inc.) devices), is secret data, typically a string of characters, usually used to confirm a user's identity.  
~ More on source [Wikipedia](https://en.wikipedia.org/wiki/Password)

[[def: payload, payload]]

~ The term 'payload' is used to distinguish between the 'interesting' information in a chunk of data or similar and the overhead to support it. The payload refers to the interesting part.

[[def: pdf, pdf-document]]

~ A document in the standard portable document format "pdf"-format

[[def: peer-to-peer, peer to peer]]

~ Peer-to-peer (P2P) computing or networking is a [distributed application](https://en.wikipedia.org/wiki/Distributed_application) architecture that partitions tasks or workloads between peers. Peers are **equally privileged**, [equipotent](https://en.wikipedia.org/wiki/Equipotent) participants in the network. They are said to form a peer-to-peer network of [nodes](https://en.wikipedia.org/wiki/Node_(networking))

~ More on source [Wikipedia](https://en.wikipedia.org/wiki/Peer-to-peer) 

[[def: perfect-security, perfect security]]

~ a special case of Information theoretic security [[ref: itps]].  
~ Source: Dr. S. Smith

[[def: persistent-data-structure, persistent data structure]]

~ An append only verifiable data structure. What we sign may not change.

[[def: PGP, PGP]]

~ [[ref: pretty-good-privacy]]

[[def: pipelining, pipelining]]

~ In [computing](https://en.wikipedia.org/wiki/Computing), a pipeline, also known as a data pipeline, is a set of [data](https://en.wikipedia.org/wiki/Data) processing elements connected in series, where the output of one element is the input of the next one. The elements of a pipeline are often executed in parallel or in time-sliced fashion. Some amount of [buffer storage](https://en.wikipedia.org/wiki/Buffer_(computer_science)) is often inserted between elements.  
~ More on source [Wikipedia-page](https://en.wikipedia.org/wiki/Pipeline_(computing))

[[def: PKI, PKI]]

~ [[ref: public-key-infrastructure]]

[[def: post-pad, post pad]]

~ the action and / or result of extending a string with _trailing_ pad characters to align to a certain length in bits or bytes.

[[def: post-quantum, post quantum]]

~ In cryptography, post-quantum cryptography (PQC) (sometimes referred to as quantum-proof, quantum-safe or quantum-resistant) refers to cryptographic algorithms (usually public-key algorithms) that are thought to be secure against a cryptanalytic attack by a quantum computer.  
~ More on source [Wikipedia](https://en.wikipedia.org/wiki/Post-quantum_cryptography)

[[def: pre-pad, pre pad]]

~ the action and / or result of prepending a string with _leading_ pad characters to align to a certain length in bits or bytes.

[[def: pretty-good-privacy, pretty good privacy]]

~ Is an encryption program that provides cryptographic privacy and authentication for data communication. PGP is used for signing, encrypting, and decrypting texts, e-mails, files, directories, and whole disk partitions and to increase the security of e-mail communications. Phil Zimmermann developed PGP in 1991.  
~ More on [wikipedia](https://en.wikipedia.org/wiki/Pretty_Good_Privacy)  
~ So also the often confusing [[ref: GPG]] term.

[[def: primitive, primitive]]

~ a serialization of a unitary value. All Primitives in KERI must be expressed in [[ref: composable-event-streaming-representation]].  
~ Source: Dr. S.Smith

[[def: privacy, privacy]]

~ Privacy is the ability of an individual or group to seclude themselves or information about themselves, and thereby express themselves selectively.

~ The domain of privacy partially overlaps with [security](https://en.wikipedia.org/wiki/Security), which can include the concepts of appropriate use and protection of information. Privacy may also take the form of [bodily integrity](https://en.wikipedia.org/wiki/Bodily_integrity).  
~ More on source [Wikipedia](https://en.wikipedia.org/wiki/Privacy)

[[def: PRNG, PRNG]]

~ means "Pseudorandom Number Generator" which means that a sequence of numbers (bits, bytes...) is produced from an algorithm which looks random, but is in fact deterministic (the sequence is generated from some unknown internal state), hence pseudorandom.

~ Such pseudorandomness can be cryptographically secure, or not. It is cryptographically secure if nobody can reliably distinguish the output from true randomness, even if the PRNG algorithm is perfectly known (but not its internal state). A non-cryptographically secure PRNG would fool basic statistical tests but can be distinguished from true randomness by an intelligent attacker.  
~ (Source: https://crypto.stackexchange.com/questions/12436/what-is-the-difference-between-csprng-and-prng)

[[def: proof-of-authority, proof of authority]]

~ Proof that somebody or something has certain rights or permissions. It's about _data_. Whereas [[ref: proof-of-authorship]] is about _data_ and its original creator.  
~ A proof-of-authority provides verifiable authorizations or permissions or rights or credentials.

[[def: protocol, protocol]]

~ Generic term to describe a code of correct conduct. Also called "[etiquette](https://en.wikipedia.org/wiki/Etiquette)": a code of personal behavior.

[[def: provenance, provenance]]

~ From Wikipedia ([Source](https://en.wikipedia.org/wiki/Provenance)):

~ Provenance (from the [French](https://en.wikipedia.org/wiki/French_language) provenir, 'to come from/forth') is the chronology of the ownership, custody or location of a historical object. The term was originally mostly used in relation to [works of art](https://en.wikipedia.org/wiki/Works_of_art) but is now used in similar senses in a wide range of fields, including [archaeology](https://en.wikipedia.org/wiki/Archaeology), [paleontology](https://en.wikipedia.org/wiki/Paleontology), [archives](https://en.wikipedia.org/wiki/Archive), [manuscripts](https://en.wikipedia.org/wiki/Manuscript), printed books, the [circular economy](https://en.wikipedia.org/wiki/Circular_economy), and science and computing.

[[def: pseudo-random-number, pseudo-random number]]

~ A (set of) value(s) or element(s) that is statistically random, but it is derived from a known starting point and is typically repeated over and over. 

[[def: public-key-infrastructure, public key infrastructure]]

~ Is a set of roles, policies, hardware, software and procedures needed to create, manage, distribute, use, store and revoke digital certificates and manage public-key encryption.

~ <img src="https://github.com/WebOfTrust/keri/blob/main/images/pubprivkey-caveat.png?raw=true" alt="Public Private Key caveat to KERI" border="0" width="400"/>

~ More on [Wikipedia](https://en.wikipedia.org/wiki/Public_key_infrastructure)

[[def: race-condition, race condition]]

~ A race condition or race hazard is the condition of an electronics, software, or other system where the system's substantive behavior is dependent on the sequence or timing of other uncontrollable events. It becomes a bug when one or more of the possible behaviors is undesirable.  
~ [Source](https://en.wikipedia.org/wiki/Race_condition).

[[def: rainbow-table-attack, rainbow table attack]]

~ A rainbow table attack is a password-cracking method that uses a special table (a “rainbow table”) to crack the password hashes in a database. 

[[def: registry, registry]]

~ In our digital mental model it's an _official_ digital _record book_. When people refer to a registry, they usually mean a specific instance, within a multi-tenant registry. E.g. [Docker Hub](https://hub.docker.com/) is a multi-tenant registry, where there’s a set of [official / public images](https://docs.docker.com/docker-hub/official_images/).

[[def: replay-attack, replay attack]]

~ A _replay attack_ occurs when a cybercriminal eavesdrops on a secure network communication, intercepts it, and then fraudulently delays or resends it to misdirect the receiver into doing what the hacker wants. 

[[def: repo, repo]]

~ Software is our line of work. In this, 'repo' is the short hand for 'Repository', mostly referring to a software repo(sitory) on [Github.com](https://github.com), Gitlab (https://gitlab.com) or other software repository hosting services. 

[[def: revocation, revocation]]

~ Revocation is the act of [recall](https://en.wiktionary.org/wiki/recall) or [annulment](https://en.wikipedia.org/wiki/Annulment). It is the cancelling of an act, the recalling of a grant or privilege, or the making [void](https://en.wikipedia.org/wiki/Void_(law)) of some [deed](https://en.wikipedia.org/wiki/Deed) previously existing.  
~ More on source [Wikipedia](https://en.wikipedia.org/wiki/Revocation)

[[def: ricardian-contract, ricardian contract]]

~ The Ricardian contract, as invented by Ian Grigg in 1996, is a method of recording a document as a [contract](https://en.wikipedia.org/wiki/Contract) at law, and linking it securely to other systems, such as accounting, for the contract as an issuance of value.

[[def: root-of-trust, root of trust]]

~ A root-of-trust is some component of a system that is [[ref: security]] by design and its security characteristics may be inherently trusted or relied upon by other components of the system.

[[def: salt, salt]]

~ random data fed as an additional input to a one-way function that hashes data.  
~ Source: Dr. S. Smith

[[def: schema-namespace-registry, schema namespace registry]]

~ a centrally managed [[ref: schema-registry]] where corporations or individuals reserve schemas within a specific [[ref: namespace]] in order to have an interoperable schema that is labeled with a corporation-specific or individual-specific namespace. 

[[def: schema-registry, schema registry]]

~ Central [[ref: registry]] for credential schemas based on namespaces. 

[[def: seal]]

~ a seal is a cryptographic commitment in the form of a cryptographic digest or hash tree root (Merkle root) that anchors arbitrary data or a tree of hashes of arbitrary data to a particular event in the key event sequence.  
~ Source: Dr. S. Smith

[[def: Secure Sockets Layer, SSL]]

~ The original transport layer security protocol developed by Netscape and partners. Now deprecated in favor of [[ref: Transport Layer Security]] (TLS).

~ Also known as: [[ref: SSL]].

[[def: security-overlay-properties-trillema, security overlay properties trillema]]

~ An identifier system has some degree of any combination of the three properties [[ref: authenticity]], [[ref: privacy]] and [[ref: confidentiality]], but not all three completely.

[[def: seed, seed]]

~ In cryptography a 'seed' is a _pseudorandomly_ generated number, often expressed in representation of a series of words.  
~ Paraphrased from [wikipedia](https://en.wikipedia.org/wiki/Random_seed)

[[def: self-sovereignty, self sovereignty]]

~ [Self sovereignty](https://github.com/trustoverip/toip/wiki/self-sovereignty) in Trust over IP wiki.

[[def: semver, semver]]

~ Semantic Versioning Specification 2.0. See also (https://semver.org/)[https://semver.org/].  
~ Source: Dr. S.Smith

[[def: service-endpoint, service endpoint]]

~ In our context we consider a **web service endpoint** which is a [[ref: uniform-resource-locator]] at which clients of specific service can get access to the service.

[[def: service-level-agreement, Service Level Agreement, SLA]] 

~ A document that contains detailed descriptions of the services to be provided by service parties and the service level requirements expected for these services.

~ [Source](https://www.gleif.org/vlei/introducing-the-vlei-ecosystem-governance-framework/2023-12-15_vlei-egf-v2.0-glossary_v1.3_final.pdf) verifiable LEI (vLEI) Ecosystem Governance Framework Glossary

[[def: side-channel-attack, side-channel attack]]

~ any attack that extracts secrets by observing indirect information leaked by a system — things like how long it takes to do an operation, how much power it uses, emitted radio/EM noise, cache behavior, or even tiny sounds — rather than breaking the cryptography or protocol directly.

~ More: [Wikipedia](https://en.wikipedia.org/wiki/Side-channel_attack)

[[def: signed-digest, signed digest]]

~ commitment to content, by digitally signing a digest of this content.

[[def: signing-threshold, signing threshold]]

~ Is the minimum number of valid signatures to satisfy the requirement for successful verification in a [[ref: threshold-signature-scheme]].

[[def: source-of-truth, source of truth]]

~ The source of truth is a trusted data source that gives a complete picture of the data object as a whole.  
~ [Source](https://www.linkedin.com/pulse/difference-between-system-record-source-truth-santosh-kudva/): LinkedIN.

[[def: spanning-layer, spanning layer]]

~ An all encompassing layer horizontal layer in a software architecture. Each trust layer only spans platform specific applications. It bifurcates the internet trust map into domain silos (e.g. twitter.com), because there is no spanning trust layer.

~ ![](https://github.com/WebOfTrust/keri/blob/main/images/spanning_layer.png)

[[def: SSL]]

~ See: [[ref: Secure Sockets Layer]].

[[def: sub-shell, sub shell]]

~ A subshell is basically a new shell just to run a desired program. A subshell can access the global variables set by the 'parent shell' but not the local variables. Any changes made by a subshell to a global variable is not passed to the parent shell.  
~ [Source](https://linuxhandbook.com/subshell/)

[[def: supermajority, supermajority]]

~ Sufficient majority that is labeled _immune_ from certain kinds of attacks or faults.

[[def: tcp-endpoint, tcp endpoint]]

~ This is a [[ref: service-endpoint]] of the web [[ref: transmission-control-protocol]]

[[def: TCP]]

~ [[ref: transmission-control-protocol]]

[[def: TEE, TEE]]

~ [[ref: trusted-execution-environment]]

[[def: threshold-structure-security, threshold structure security]]

~ A threshold structure for security allows for weaker key management or execution environment infrastructure individually, but achieve greater overall security by multiplying the number of attack surfaces that an attacker must overcome to compromise a system.

[[def: TPM, TPM]]

~ [[ref: trusted-platform-module]]

[[def: trans-contextual-value, trans-contextual value]]

~ Value that is transferrable between contexts. **How do we recapture the value in our data?** 1- Leverage cooperative network effects 2- Retake control of our data.   
~ [Source](https://github.com/SmithSamuelM/Papers/blob/master/presentations/NonconformistKeynoteWeb20200702.pdf) Samuel Smith

[[def: Transmission Control Protocol, TCP]]

~ The Transmission Control Protocol (TCP) is one of the main protocols of the [[ref: Internet protocol suite]]. It originated in the initial network implementation in which it complemented the [[ref: Internet Protocol]] (IP). Therefore, the entire suite is commonly referred to as [[ref: TCP/IP]]. TCP provides reliable, ordered, and error-checked delivery of a stream of octets (bytes) between applications running on hosts communicating via an IP network. Major internet applications such as the World Wide Web, email, remote administration, and file transfer rely on TCP, which is part of the Transport Layer of the TCP/IP suite. [[ref: SSL]]/[[ref: TLS]] often runs on top of TCP.

~ Source: [Wikipedia](https://en.wikipedia.org/wiki/Transmission_Control_Protocol).

~ Also known as: [[ref: TCP]].

~ See also: [[xref: toip1, user-datagram-protocol, User Datagram Protocol]].

[[def: tritet, Tritet]]

~ 3 bits. See [Performant resynchronization with unique start bits](https://trustoverip.github.io/kswg-cesr-specification/#performant-resynchronization-with-unique-start-bits).  
~ Source: Dr. S. Smith

[[def: trusted-execution-environment, trusted execution environment]]

~ Protected hardware/software/firmware security system. The controller may protect its key generation, key storage, and event signing infrastructure by running it inside a trusted execution environment (TEE). 

[[def: trusted-platform-module, trusted platform module]]

~  A device that enhances the security and privacy (of identity systems) by providing hardware-based cryptographic functions. 

~  ## Functions
~  A TPM can generate, store, and protect encryption keys and authentication credentials that are used to verify the identity of a user or a device.  
~  A TPM can also measure and attest the integrity of the software and firmware that are running on a system, to ensure that they have not been tampered with or compromised. 

~  ## Form
~  A TPM can be implemented as a physical chip, a firmware module, or a virtual device.

~ Source: Bing chat sept 2023

[[def: ts-node, ts node]]

~ npm package that lets you run typescript from a shell

[[def: UI, UI]]

~ [[ref: user-interface]]

[[def: uniform-resource-locator, uniform resource locator]]

~ A Uniform Resource Locator (URL), colloquially termed a web address, is a reference to a [web resource](https://en.wikipedia.org/wiki/Web_resource) that specifies its location on a [computer network](https://en.wikipedia.org/wiki/Computer_network) and a mechanism for retrieving it. 

[[def: URL, URL]]

~ [[ref: uniform-resource-locator]]

[[def: user-interface, user interface]]

~ A user interface (UI or U/I) is the space where interactions between humans and machines occur.

[[def: validate, validate]]

~ ESSIF-lab definition of _[validate](https://essif-lab.github.io/framework/docs/essifLab-glossary#validate)_. Although this definition is very general, in the KERI/ACDC vocabulary, 'validate' currently has extra diverse meanings extending the one of eSSIF-lab, such as
~ - evaluate
~ - [[ref: verify]]

[[def: validator, validators]]

~ any entity or agent that evaluates whether or not a given signed statement as attributed to an identifier is valid at the time of its issuance.  
~ Source: Dr. S. Smith

[[def: variable-length, variable length]]

~ a type of count code allowing for vaiable size signatures or attachments which can be parsed to get the full size.  
~ Source: Dr. S. Smith

[[def: VC, VC]]

~ [[ref: verifiable-credential]]

[[def: VDS, VDS]]

~ [[ref: verifiable-data-structure]]

[[def: veracity, veracity]]

~ The quality of being true; contrast [[ref: authenticity]]. When a newspaper publishes a story about an event, every faithful reproduction of that story may be *authentic* — but that does not mean the story was true (has *veracity*).

[[def: verifiable-data-registry, verifiable data registry]]

~ A role a system might perform by mediating issuance and verification of ACDCs. See [verifiable data registry](https://www.w3.org/TR/vc-data-model-2.0/#dfn-verifiable-data-registries).  
~ Source: Dr. S. Smith

[[def: verifiable-data-structure, verifiable data structure]]

~ A verifiable data structure is a data structure that incorporates cryptographic techniques to ensure the integrity and authenticity of its contents. It allows users to verify the correctness of the data stored within the structure without relying on a trusted third party.
~ [[ref: #Sources-Definition-ChatGPT]]

[[def: verified-integrity, verified integrity]]

~ A mechanism that can unambiguously assess whether the information is/continues to be whole, sound and unimpaired

[[def: verifier, verifier]]

~ any entity or agent that cryptographically verifies the signature(s) and digests on an event Message.  
~ Source Dr. S. Smith

[[def: verify-signature, verify signature]]

~ Applying an algorithm that, given the message, public key and signature, either accepts or rejects the message's claim to authenticity.

[[def: wallet, wallet]]

~ A crypto wallet is a device, physical medium, program or a service which stores the [public and/or private keys](https://en.wikipedia.org/wiki/Public-key_cryptography) for [cryptocurrency](https://en.wikipedia.org/wiki/Cryptocurrency) transactions and digital identifiers.  
~ Paraphrased by @henkvancann from source [Wikipedia](https://en.wikipedia.org/wiki/Cryptocurrency_wallet)

[[def: web-of-trust, web of trust]]

~ In cryptography, a web of trust is a concept used in [[ref: PGP]], [[ref: gnu-privacy-guard]], and other `OpenPGP`-compatible systems to establish the authenticity of the binding between a public key and its owner.

[[def: XBRL, XBRL]]

~ [[ref: extensible-business-reporting-language]]

[[def: zero-trust-computing, zero-trust computing]]

~ A security model centered on the principle of "never trust, always verify." It assumes that threats can exist inside and outside the network, and thus, no entity — a device, user, or system — is inherently trusted. This approach requires continuous verification of all users and devices attempting to access network resources.

[[def: zero-trust, zero trust]]

~ a Zero Trust approach trusts no one.

