did:x509 Method Specification
==================

**Specification Status**: v1.0 Draft

**Latest Draft:**

[https://github.com/trustoverip/tswg-did-x509-method-specification](https://github.com/trustoverip/tswg-did-x509-method-specification)

**Abstract:**

The `did:x509` method aims to achieve interoperability between existing X.509 solutions and Decentralized Identifiers (DIDs) to support operational models in which a full transition to DIDs is not achievable or desired yet. It supports X.509-only verifiers as well as DID-based verifiers supporting this DID method.

**Editors:**

- [Eric Scouten](https://github.com/scouten-adobe), [Adobe](https://adobe.com)
- Wenjing Chu, Futurewei

**Contributors:**

- [Maik Riechert](https://github.com/letmaik), [Microsoft](https://microsoft.com)
- [Antoine Delignat-Lavaud](https://github.com/ad-l), [Microsoft](https://microsoft.com)

**Participate:**

~ [GitHub repo](https://github.com/trustoverip/tswg-did-x509-method-specification)
~ [Commit history](https://github.com/trustoverip/tswg-did-x509-method-specification/commits/main)

------------------------------------

[//]: # (Pandoc Formatting Macros)

[//]: # (\maketitle)

[//]: # (\newpage)
## Status of This Memo

This document contains a working draft for the specification for the `did:x509` DID method.

Information about the current status of this document, any errata,
and how to provide feedback on it, may be obtained at
[https://github.com/trustoverip/tswg-did-x509-method-specification](https://github.com/trustoverip/tswg-did-x509-method-specification).

## Copyright Notice

This specification is subject to the **OWF Contributor License Agreement 1.0 - Copyright**
available at
[https://www.openwebfoundation.org/the-agreements/the-owf-1-0-agreements-granted-claims/owf-contributor-license-agreement-1-0-copyright](https://www.openwebfoundation.org/the-agreements/the-owf-1-0-agreements-granted-claims/owf-contributor-license-agreement-1-0-copyright).

If source code is included in the specification, that code is subject to the
Apache 2.0 license unless otherwise marked. In the case of any conflict or
confusion within this specification between the OWF Contributor License 
and the designated source code license, the terms of the OWF Contributor License shall apply.

These terms are inherited from the Technical Stack Working Group at the Trust over IP Foundation. [Working Group Charter](https://trustoverip.org/wp-content/uploads/TSWG-2-Charter-Revision.pdf)

## Terms of Use

These materials are made available under and are subject to the [OWF CLA 1.0 - Copyright & Patent license](https://www.openwebfoundation.org/the-agreements/the-owf-1-0-agreements-granted-claims/owf-contributor-license-agreement-1-0-copyright-and-patent). Any source code is made available under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0.txt).

THESE MATERIALS ARE PROVIDED “AS IS.” The Trust Over IP Foundation, established as the Joint Development Foundation Projects, LLC, Trust Over IP Foundation Series ("ToIP"), and its members and contributors (each of ToIP, its members and contributors, a "ToIP Party") expressly disclaim any warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to the materials. The entire risk as to implementing or otherwise using the materials is assumed by the implementer and user. 
IN NO EVENT WILL ANY ToIP PARTY BE LIABLE TO ANY OTHER PARTY FOR LOST PROFITS OR ANY FORM OF INDIRECT, SPECIAL, INCIDENTAL, OR CONSEQUENTIAL DAMAGES OF ANY CHARACTER FROM ANY CAUSES OF ACTION OF ANY KIND WITH RESPECT TO THESE MATERIALS, ANY DELIVERABLE OR THE ToIP GOVERNING AGREEMENT, WHETHER BASED ON BREACH OF CONTRACT, TORT (INCLUDING NEGLIGENCE), OR OTHERWISE, AND WHETHER OR NOT THE OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

## RFC 2119

The Internet Engineering Task Force (IETF) is a large open international community of network designers, operators, vendors, and researchers concerned with the evolution of the Internet architecture and to ensure maximal efficiency in operation. IETF has been operating since the advent of the Internet using a Request for Comments (RFC) to convey “current best practice” to those organizations seeking its guidance for conformance purposes.

The IETF uses RFC 2119 to define keywords for use in RFC documents; these keywords are used to signify applicability requirements. ToIP has adapted the IETF RFC 2119 for use in the `did:x509` Method Specification, and therefore its applicable use in ToIP-compliant governance frameworks.

The RFC 2119 keyword definitions and interpretation have been adopted. Those users who follow these guidelines SHOULD incorporate the following phrase near the beginning of their document:

> The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC 2119.

RFC 2119 defines these keywords as follows:

 * MUST: This word, or the terms "REQUIRED" or "SHALL", mean that the definition is an absolute requirement of the specification.
 * MUST NOT: This phrase, or the phrase "SHALL NOT", means that the definition is an absolute prohibition of the specification.
 * SHOULD: This word, or the adjective "RECOMMENDED", means that there MAY exist valid reasons in particular circumstances to ignore a particular item, but the full implications MUST be understood and carefully weighed before choosing a different course.
 * SHOULD NOT: This phrase, or the phrase "NOT RECOMMENDED" means that there MAY exist valid reasons in particular circumstances when the particular behavior is acceptable or even useful, but the full implications SHOULD be understood, and the case carefully weighed before implementing any behavior described with this label.
 * MAY: This word, or the adjective "OPTIONAL", means that an item is truly optional.  One vendor MAY choose to include the item because a particular marketplace requires it or because the vendor feels that it enhances the product while another vendor MAY omit the same item.

Requirements include any combination of Machine-Testable Requirements and Human-Auditable Requirements. Unless otherwise stated, all Requirements MUST be expressed as defined in RFC 2119.

 * Mandatories are Requirements that use a MUST, MUST NOT, SHALL, SHALL NOT or REQUIRED keyword.
 * Recommendations are Requirements that use a SHOULD, SHOULD NOT, or RECOMMENDED keyword.
 * Options are Requirements that use a MAY or OPTIONAL keyword.

An implementation which does not include a particular option MUST be prepared to interoperate with other implementations which include the option, recognizing the potential for reduced functionality. As well, implementations which include a particular option MUST be prepared to interoperate with implementations which do not include the option and the subsequent lack of function the feature provides.


[//]: # (Pandoc Formatting Macros)

[//]: # (\toc)


[//]: # (::: forewordtitle)

[//]: # (Foreword)

[//]: # (:::)

## Foreword

This publicly available specification was approved by the ToIP Foundation Steering Committee on [dd month yyyy must match date in subtitle above]. The ToIP permalink for this document is:

            [permalink for this deliverable: see instructions on this [wiki page](https://wiki.trustoverip.org/display/HOME/File+Names+and+Permalinks)]

The mission of the Trust over IP (ToIP) Foundation is to define a complete architecture for Internet-scale digital trust that combines cryptographic assurance at the machine layer with human accountability at the business, legal, and social layers. Founded in May 2020 as a non-profit hosted by the Linux Foundation, the ToIP Foundation has over 400 organizational and 100 individual members from around the world.

Any trade name used in this document is information given for the convenience of users and does not constitute an endorsement.

This document was prepared by the ToIP Technical Stack Working Group.

Any feedback or questions on this document should be directed to https://github.com/trustoverip/specification/issues

THESE MATERIALS ARE PROVIDED “AS IS.” The Trust Over IP Foundation, established as the Joint Development Foundation Projects, LLC, Trust Over IP Foundation Series ("ToIP"), and its members and contributors (each of ToIP, its members and contributors, a "ToIP Party") expressly disclaim any warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to the materials. The entire risk as to implementing or otherwise using the materials is assumed by the implementer and user. 
IN NO EVENT WILL ANY ToIP PARTY BE LIABLE TO ANY OTHER PARTY FOR LOST PROFITS OR ANY FORM OF INDIRECT, SPECIAL, INCIDENTAL, OR CONSEQUENTIAL DAMAGES OF ANY CHARACTER FROM ANY CAUSES OF ACTION OF ANY KIND WITH RESPECT TO THESE MATERIALS, ANY DELIVERABLE OR THE ToIP GOVERNING AGREEMENT, WHETHER BASED ON BREACH OF CONTRACT, TORT (INCLUDING NEGLIGENCE), OR OTHERWISE, AND WHETHER OR NOT THE OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

[//]: # (\newpage)

[//]: # (Pandoc Formatting Macros)

[//]: # (::: introtitle)

[//]: # (Introduction)

[//]: # (:::)

## Introduction

The RWOT11 workshop outlined the need for hybrid solutions that combine X.509 certificates with DIDs: ["Analysis of hybrid wallet solutions - Implementation options for combining x509 certificates with DIDs and VCs"](https://github.com/WebOfTrustInfo/rwot11-the-hague/blob/master/advance-readings/hybrid_wallet_solutions_x509_DIDs_VCs.md).

The `did:x509` method takes a simple approach that does not introduce additional infrastructure. Creating and resolving a `did:x509` is a local operation. It relies on X.509 chain validation and matches elements contained in the DID to certificate properties within the chain.

The main difference to other DID methods is that `did:x509` requires a certificate chain to be passed using a new [DID resolution option](https://www.w3.org/TR/did-core/#did-resolution-options) `x509chain` while resolving a DID. This certificate chain is typically embedded in the signing envelope, for example within the `x5c` header parameter of JWS/JWT documents.

This work is derived from a draft `did:x509` method specification published by Maik Riechert and Antoine Delignat-Lavaud of Microsoft which is published here: https://github.com/microsoft/did-x509.


[//]: # (Pandoc Formatting Macros)

[//]: # (\mainmatter)

[//]: # (\doctitle)

## Scope

The [X.509 VID Task Force](https://wiki.trustoverip.org/pages/viewpage.action?pageId=68453176) (X5VTF) is a task force of the ToIP [Technology Stack Working Group](https://wiki.trustoverip.org/display/HOME/Technology+Stack+Working+Group), which intends to explore how X.509 identifiers can be part of the ToIP verifiable identifier landscape.

The deliverable of this Task Force is the **did:x509 Method Specification** that must meet the requirements of a verifiable identifier (VID) as specified in the [ToIP Technology Architecture V1.0 Specification](https://trustoverip.org/our-work/technical-architecture/) and the draft [ToIP Trust Spanning Protocol Specification](https://wiki.trustoverip.org/display/HOME/ToIP+Trust+Spanning+Protocol+Specification). The requirements in this specification must interoperate with other ToIP component specifications as explained in the [Evolution of the ToIP Stack](https://trustoverip.org/our-work/evolution-of-the-toip-stack/).

## Example

`did:x509:0:sha256:WE4P5dd8DnLHSkyHaIjhp4udlkF9LqoKwCvu9gl38jk::subject:C:US:ST:California:O:My%20Organisation`

In this example, the identifier pins to a certificate authority using the SHA-256 certificate hash and uses the `subject` policy to express criteria which a leaf certificate's subject must fulfill. This identifier will match any certificate chains with matching leaf certificate subject fields and a matching intermediate or root CA certificate.

## JSON data model for X.509 certificate chains

This section defines a JSON data model for X.509 certificate chains that is the basis for evaluating whether a certificate chain matches a given `did:x509` identifier. The language used for defining the JSON data model is CDDL ([RFC 8610](https://www.rfc-editor.org/rfc/rfc8610)).

```cddl
CertificateChain = [2*Certificate]  ; leaf is first

Certificate = {
    fingerprint: {
        ; base64url-encoded hashes of the DER-encoded certificate
        sha256: base64url,     ; FIPS 180-4, SHA-256
        sha384: base64url,     ; FIPS 180-4, SHA-384
        sha512: base64url      ; FIPS 180-4, SHA-512
    },
    issuer: Name,              ; RFC 5280, Section 4.1.2.4
    subject: Name,             ; RFC 5280, Section 4.1.2.6
    extensions: {
        ? eku: [+OID],         ; RFC 5280, Section 4.2.1.12
        ? san: [+SAN],         ; RFC 5280, Section 4.2.1.6
        ? fulcio_issuer: tstr  ; http://oid-info.com/get/1.3.6.1.4.1.57264.1.1
    }
}

; X.509 Name as an object of attributes
; Repeated attribute types are not supported
; Common attribute types have human-readable labels (see below)
; Other attribute types use dotted OIDs
; Values are converted to UTF-8
Name = {
    ; See RFC 4514, Section 3, for meaning of common attribute types
    ? CN: tstr,
    ? L: tstr,
    ? ST: tstr,
    ? O: tstr,
    ? OU: tstr,
    ? C: tstr,
    ? STREET: tstr,
    * OID => tstr
}

; base64url-encoded data, see RFC 4648, Section 5
base64url = tstr

; ASN.1 Object Identifier
; Dotted string, for example "1.2.3"
OID = tstr

; X.509 Subject Alternative Name
; Strings are converted to UTF-8
SAN = rfc822Name / DNSName / URI / DirectoryName
rfc822Name = ["email", tstr] ; Example: ["email", "bill@microsoft.com"]
DNSName = ["dns", tstr]      ; Example: ["dns", "microsoft.com"]
URI = ["uri", tstr]          ; Example: ["uri", "https://microsoft.com"]
DirectoryName = ["dn", Name] ; Example: ["dn", {CN: "Microsoft"}]
```

In the rest of this document, `chain` refers to the certificate chain mapped to the above JSON data model.

## Identifier Syntax

::: issue
https://github.com/trustoverip/tswg-did-x509-method-specification/issues/5: Planned review by of this section by task force
:::

The `did:x509` ABNF definition can be found below, which uses the syntax in [RFC 5234](https://www.rfc-editor.org/rfc/rfc5234.html) and the corresponding definitions for `ALPHA` and `DIGIT`. The [W3C DID v1.0 specification](https://www.w3.org/TR/2022/REC-did-core-20220719/) contains the definition for `idchar`.

```abnf
did-x509           = "did:" method-name ":" method-specific-id
method-name        = "x509"
method-specific-id = version ":" ca-fingerprint-alg ":" ca-fingerprint 1*("::" policy-name ":" policy-value)
version            = 1*DIGIT
ca-fingerprint-alg = "sha256" / "sha384" / "sha512"
ca-fingerprint     = base64url
policy-name        = 1*ALPHA
policy-value       = *(1*idchar ":") 1*idchar
base64url          = 1*(ALPHA / DIGIT / "-" / "_")
```

In this draft, version is `0`.

`ca-fingerprint-alg` is one of `sha256`, `sha384`, or `sha512`.

`ca-fingerprint` is `chain[i].fingerprint[ca-fingerprint-alg]` with i > 0, that is, either an intermediate or root CA certificate.

`policy-name` is a policy name and `policy-value` is a policy-specific value. 

`::` is used to separate multiple policies from each other.

The following sections define the policies and their policy-specific syntax.

::: issue
https://github.com/trustoverip/tswg-did-x509-method-specification/issues/8: Re-evaluate Rego vs alternative descriptions of policy.
:::

Validation of policies is formally defined using [Rego policies](https://www.openpolicyagent.org/docs/latest/policy-language/), though there is no expectation that implementations use Rego.

The input to the Rego engine is the JSON document `{"did": "<DID>", "chain": <CertificateChain>}`.

Core Rego policy:

```rego
import future.keywords.if
import future.keywords.in

parse_did(did) := [ca_fingerprint_alg, ca_fingerprint, policies] if {
    prefix := "did:x509:0:"
    startswith(did, prefix) == true
    rest := trim_prefix(did, prefix)
    parts := split(rest, "::")
    [ca_fingerprint_alg, ca_fingerprint] := split(parts[0], ":")
    policies_raw := array.slice(parts, 1, count(parts))
    policies := [y |
        some i
        s := policies_raw[i]
        j := indexof(s, ":")
        y := [substring(s, 0, j), substring(s, j+1, -1)]
    ]
}

valid if {
    [ca_fingerprint_alg, ca_fingerprint, policies] := parse_did(input.did)
    ca := [c | some i; i != 0; c := input.chain[i]]
    ca[_].fingerprint[ca_fingerprint_alg] == ca_fingerprint
    valid_policies := [i |
        some i
        [name, value] := policies[i]
        validate_policy(name, value)
    ]
    count(valid_policies) == count(policies)
}
```

The overall Rego policy is assembled by concatenating the core Rego policy with the Rego policy fragments in the following sections, each one defining a `validate_policy` function.

### Percent-encoding

::: issue
https://github.com/trustoverip/tswg-did-x509-method-specification/issues/4: Can this section be rewritten more fully in terms of RFC 3986?
:::

Some of the policies that are defined in subsequent sections require values to be percent-encoded. Percent-encoding is specified in [RFC 3986 Section 2.1](https://www.rfc-editor.org/rfc/rfc3986#section-2.1). All characters that are not in the allowed set defined below must be percent-encoded:

```abnf
allowed = ALPHA / DIGIT / "-" / "." / "_"
```

Note that most libraries implement percent-encoding in the context of URLs and do NOT encode `~` (`%7E`).

### `subject` policy

```abnf
policy-name     = "subject"
policy-value    = key ":" value *(":" key ":" value)
key             = label / oid
value           = 1*idchar
label           = "CN" / "L" / "ST" / "O" / "OU" / "C" / "STREET"
oid             = 1*DIGIT *("." 1*DIGIT)
```

`<key>:<value>` are the subject name fields in `chain[0].subject` in any order. Field repetitions are not allowed. Values must be percent-encoded.

Example:

`did:x509:0:sha256:WE4P5dd8DnLHSkyHaIjhp4udlkF9LqoKwCvu9gl38jk::subject:C:US:ST:California:L:San%20Francisco:O:GitHub%2C%20Inc.`

Rego policy:
```rego
validate_policy(name, value) := true if {
    name == "subject"
    items := split(value, ":")
    count(items) % 2 == 0
    subject := {k: v |
        some i
        i % 2 == 0
        k := items[i]
        v := urlquery.decode(items[i+1])
    }
    count(subject) >= 1
    object.subset(input.chain[0].subject, subject) == true
}
```

### `san` policy

```abnf
policy-name     = "san"
policy-value    = san-type ":" san-value
san-type        = "email" / "dns" / "uri"
san-value       = 1*idchar
```

`san-type` is the SAN type and must be one of `email`, `dns`, or `uri`. Note that `dn` is not supported.

`san-value` is the SAN value, percent-encoded.

The pair [`<san_type>`, `<san_value>`] is one of the items in `chain[0].extensions.san`.

Example: 

`did:x509:0:sha256:WE4P5dd8DnLHSkyHaIjhp4udlkF9LqoKwCvu9gl38jk::san:email:bob%40example.com`

Rego policy:

```rego
validate_policy(name, value) := true if {
    name == "san"
    [san_type, san_value_encoded] := split(value, ":")
    san_value := urlquery.decode(san_value_encoded)
    [san_type, san_value] == input.chain[0].extensions.san[_]
}
```

### `eku` policy

```abnf
policy-name  = "eku"
policy-value = eku
eku          = oid
oid          = 1*DIGIT *("." 1*DIGIT)
```

`eku` is one of the OIDs within `chain[0].extensions.eku`.

Example:

`did:x509:0:sha256:WE4P5dd8DnLHSkyHaIjhp4udlkF9LqoKwCvu9gl38jk::eku:1.3.6.1.4.1.311.10.3.13`

Rego policy:

```rego
validate_policy(name, value) := true if {
    name == "eku"
    value == input.chain[0].extensions.eku[_]
}
```

### `fulcio-issuer` policy

```abnf
policy-name   = "fulcio-issuer"
policy-value  = fulcio-issuer
fulcio-issuer = 1*idchar
```

`fulcio-issuer` is `chain[0].extensions.fulcio_issuer` without leading `https://`, percent-encoded. 

Example:

`did:x509:0:sha256:WE4P5dd8DnLHSkyHaIjhp4udlkF9LqoKwCvu9gl38jk::fulcio-issuer:accounts.google.com::san:email:bob%40example.com`

Example 2:

`did:x509:0:sha256:WE4P5dd8DnLHSkyHaIjhp4udlkF9LqoKwCvu9gl38jk::fulcio-issuer:token.actions.githubusercontent.com::san:uri:https%3A%2F%2Fgithub.com%2Focto-org%2Focto-automation%2F.github%2Fworkflows%2Foidc.yml%40refs%2Fheads%2Fmain`

Rego policy:

```rego
validate_policy(name, value) := true if {
    name == "fulcio-issuer"
    suffix := urlquery.decode(value)
    concat("", ["https://", suffix]) == input.chain[0].extensions.fulcio_issuer
}
```

## DID resolution options

::: issue 
https://github.com/trustoverip/tswg-did-x509-method-specification/issues/6: Planned review by of this section by task force
:::

This DID method introduces a new DID resolution option called `x509chain`:

Name: `x509chain`

Value type: string

The value is constructed as follows:

1. Encode each certificate `C` that is part of the chain as the string `b64url(DER(C))`.

2. Concatenate the resulting strings in order, separated by comma `","`.

## Operations

### Create

Creating a `did:x509` identifier is a local operation. The DID must be constructed according to the syntax rules in the previous sections. No other actions are required.

When constructing a `did:x509`, the first step is to determine what constitutes a logical identity within a given certificate authority. Concretely, which certificate fields does an authority use to uniquely represent an identity. After that, one or more matching policies must be chosen that allow to express such an identity as faithfully as possible.

As an example, a certificate authority may exclusively use email addresses as a way to separate identities, and it may use the SAN extension to store the email address. In that case, the `did:x509` identifier should be constructed using the `san` policy, for example, `did:x509:0:sha256:<ca-fingerprint>::san:email:bob%40example.com`. The certificate may contain other information about the identity, like full name and address, but the primary field that uniquely identifies the identity in this case is just the email address.

In other cases, an authority may not include email addresses at all and instead rely on a specific set of subject fields to separate identities. In that case, the `subject` policy should be used.

In yet other cases, authorities may assign unique numbers or other types of stable identifiers to logical identities. Typically, this is done to have a stable reference even if a person changes their name or email address.

In all cases, the goal is to craft a `did:x509` that is both stable yet not too loose in its policies. An example of a loose `did:x509` may be to use the `subject` policy and only include the `O` field without location fields like country (`C`) or state/locality (`ST`). See also the Security and Privacy Considerations section.

Finally, whether a `did:x509` should pin to an intermediate CA instead of a root CA (via the certificate fingerprint) depends on whether there is value in distinguishing between them. Pinning to an intermediate CA typically means that the lifetime of the `did:x509` will be shorter, since intermediate CA certificates typically have a shorter validity period than root CA certificates.

### Read

::: issue 
https://github.com/trustoverip/tswg-did-x509-method-specification/issues/10: Add discussion on timestamp of signature issuance relative to cert validity
:::

The Read operation takes as input a DID to resolve, together with the `x509chain` DID resolution option.

The following steps must be used to generate a corresponding DID document:

1. Decode the `x509chain` resolution option value into individual certificates by splitting the string on `","` and base64url-decoding each resulting string. The result is a list of DER-encoded certificates that can be loaded in standard libraries. Fail if the list contains fewer than two certificates.

2. Check whether the list of certificates form a valid certificate chain using the [RFC 5280 certification path validation](https://www.rfc-editor.org/rfc/rfc5280#section-6) procedures with the last certificate in the chain as trust anchor. If any extension, excluding the basic constraints and key usage extensions, is marked critical but is not part of the JSON data model, fail.

3. If required by the application, check whether any certificate in the chain is revoked (using CRL, OCSP, or other mechanisms).

4. Apply any further application-specific checks, for example disallowing insecure certificate signature algorithms.

5. Map the certificate chain to the JSON data model.

6. Check whether the DID is valid against the certificate chain in the JSON data model according to the Rego policy (or equivalent rules) defined in this document.

7. Extract the public key of the first certificate in the chain.

8. Convert the public key to a JSON Web Key.

9. Create the following partial DID document:

```json
{
    "@context": [
        "https://www.w3.org/ns/did/v1",
        "https://w3id.org/security/suites/jws-2020/v1"
    ],
    "id": "<DID>",
    "verificationMethod": [{
        "id": "<DID>#0",
        "type": "JsonWebKey2020",
        "controller": "<DID>",
        "publicKeyJwk": {
            // JSON Web Key
        }
    }]
}
```

10. If the first certificate in the chain has the key usage bit position for `digitalSignature` set or is missing the key usage extension, add the following to the DID document:

```json
{
    "assertionMethod": ["<DID>#0"]
}
```

11. If the first certificate in the chain has the key usage bit position for `keyAgreement` set or is missing the key usage extension, add the following to the DID document:

```json
{
    "keyAgreement": ["<DID>#0"]
}
```

12. If the first certificate in the chain includes the key usage extension but has neither `digitalSignature` nor `keyAgreement` set as key usage bits, fail.

13. Return the complete DID document.

### Update

This DID Method does not support updating the DID Document, assuming a fixed certificate chain. However, the public key included in the DID Document varies depending on the certificate chain that was used as input to the DID resolution process. Typically, multiple chains, in particular leaf certificates, are valid for a given `did:x509`.

### Deactivate

This DID Method does not support deactivating the DID. However, if the certificate authority revokes all certificates for the matching DID (or they expire) and does not issue new certificates matching the same DID, then this can be considered equivalent to deactivation of the DID, though there is no technical guarantee in this case and the certificate authority can revert its decision.

## Security and privacy considerations

### Identifier ambiguity

::: issue
https://github.com/trustoverip/tswg-did-x509-method-specification/issues/8: Review this section.
:::

This DID method maps characteristics of X.509 certificate chains to identifiers. It allows a single identifier to map to multiple certificate chains, giving the identifier stability across the expiry of individual chains. However, if the policies used in the identifier are chosen too loosely, the identifier may match too wide a set of certificate chains. This may have security implications as it may authorize an identity for actions it was not meant to be authorized for.

To mitigate this issue, the certificate authority should publish their expected usage of certificate fields and indicate which ones constitute a unique identity, versus any additional fields that may be of an informational nature. This will help users create an appropriate `did:x509` as well as consumers of signed content to decide whether it is appropriate to trust a given `did:x509`.

### X.509 trust stores

Typically, a verifier trusts an X.509 certificate by applying [chain validation](https://www.rfc-editor.org/rfc/rfc5280#section-6) (RFC 5280) using a set of certificate authority (CA) certificates as trust store, together with additional application-specific policies.

This DID method does not require an X.509 trust store but rather relies on verifiers either trusting an individual DID directly or using third-party endorsements for a given DID, like [W3C Verifiable Credentials](https://www.w3.org/TR/vc-data-model/), to establish trust.

By layering this DID method on top of X.509, verifiers are free to use traditional chain validation (for example, verifiers unaware of DID), or rely on DID as an ecosystem to establish trust.

## References

### Normative references

[Decentralized Identifiers (DIDs) v1.0](https://www.w3.org/TR/2022/REC-did-core-20220719/). Manu Sporny, Amy Guy, Markus Sabadello, Drummond Reed. W3C. 19 July 2022. W3C Recommendation.

[RFC 8610 - Concise Data Definition Language (CDDL)](https://www.rfc-editor.org/rfc/rfc8610). H. Birkholz, C. Vigano, C. Bormann. IETF. June 2019. Proposed Standard.

[RFC 5280 - Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile](https://www.rfc-editor.org/rfc/rfc5280). D. Cooper, S. Santesson, S. Farrell, S. Boeyen, R. Housley, W. Polk. IETF. May 2008. Proposed Standard.

[RFC 4514 - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names](https://www.rfc-editor.org/rfc/rfc4514). K. Zeilenga. IETF. June 2006. Proposed Standard.

[RFC 4648 - The Base16, Base32, and Base64 Data Encodings](https://www.rfc-editor.org/rfc/rfc4648). S. Josefsson. IETF. October 2006. Proposed Standard.

[RFC 5234 - Augmented BNF for Syntax Specifications: ABNF](https://www.rfc-editor.org/rfc/rfc5234.html). D. Crocker, P. Overell. IETF. January 2008.  Internet Standard.

[RFC 3986 - Uniform Resource Identifier (URI): Generic Syntax](https://www.rfc-editor.org/rfc/rfc3986). T. Berners-Lee, R. Fielding, L. Masinter. IETF. January 2005. Internet Standard.

[FIPS 180-4 - Secure Hash Standard](https://csrc.nist.gov/publications/detail/fips/180/4/final). NIST. August 2015. FIPS Publication.

### Informative references

[Analysis of hybrid wallet solutions - Implementation options for combining x509 certificates with DIDs and VCs](https://github.com/WebOfTrustInfo/rwot11-the-hague/blob/master/advance-readings/hybrid_wallet_solutions_x509_DIDs_VCs.md). Carsten Stöcker (Spherity) and Christiane Wirrig (Spherity) with support of Paul Bastian (Bundesdruckerei) and Steffen Schwalm (msg Group) in the IDunion Project. 20 July 2022. RWOT11 topic paper.

[Verifiable Credentials Data Model v1.1](https://www.w3.org/TR/2022/REC-vc-data-model-20220303/). Manu Sporny, Dave Longley, David Chadwick. W3C. 03 March 2022. W3C Recommendation.

[Rego Policy Language](https://www.openpolicyagent.org/docs/latest/policy-language/). Open Policy Agent contributors.

[Fulcio](https://github.com/sigstore/fulcio). Fulcio contributors.

