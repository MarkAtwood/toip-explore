TMCP: MCP over TSP Specification
==================

**Specification Status**: v0.1 Draft

**Latest Draft:**

[https://github.com/trustoverip/specification-template](https://github.com/trustoverip/specification-template)

**Author:**

- [Wenjing Chu](https://github.com/wenjingchu), Futurewei Technologies, Inc.

**Contributors:**

**Participate:**

~ [GitHub repo](https://github.com/trustoverip/aimwg-tmcp-specification)
~ [Commit history](https://github.com/trustoverip/aimwg-tmcp-specification/commits/main)

------------------------------------

[//]: # (Pandoc Formatting Macros)

[//]: # (\maketitle)

[//]: # (\newpage)

## Status of This Memo

This document contains a template specification for `ToIP`!.

Information about the current status of this document, any errata,
and how to provide feedback on it, may be obtained at
[https://github.com/trustoverip/specification-template](https://github.com/trustoverip/specification-template).

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

The IETF uses RFC 2119 to define keywords for use in RFC documents; these keywords are used to signify applicability requirements.  ToIP has adapted the IETF RFC 2119 for use in the <name of this document>, and therefore its applicable use in ToIP-compliant governance frameworks.

The RFC 2119 keyword definitions and interpretation have been adopted. Those users who follow these guidelines SHOULD incorporate the following phrase near the beginning of their document:
        The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in RFC 2119.

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

Fancy introduction!

[//]: # (Pandoc Formatting Macros)

[//]: # (\mainmatter)

[//]: # (\doctitle)

## Scope

Describe the scope

## Normative references

[//]: # (Pandoc Formatting Macros)

[//]: # (# Normative references)

[//]: # (::: { #nrm:pdf2 .normref label="ISO 32000-2" })

[//]: # (ISO 32000-2, *Document management --- Portable Document Format --- Part 2: PDF 2.0*)

[//]: # (:::)

[[TSP]]. Trust Spanning Protocol (TSP) Specification. Implementer's Draft, Rev 2
[[TSP]]: https://trustoverip.github.io/tswg-tsp-specification/


[//]: # (Pandoc Formatting Macros)

[//]: # (Portable Document Format)

[//]: # (blank)

[//]: # (: file format defined by ISO 32000-2)



[//]: # (Pandoc Formatting Macros)

[//]: # (Main content {#sec:content})

## Executive Summary
CoLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Mi ipsum faucibus vitae aliquet nec ullamcorper sit amet. Scelerisque fermentum dui faucibus in ornare quam viverra orci. Maecenas ultricies mi eget mauris pharetra. Tempor nec feugiat nisl pretium fusce id. In ante metus dictum at tempor commodo ullamcorper a. Nulla at volutpat diam ut venenatis tellus in. 

Quis hendrerit dolor magna eget est lorem ipsum dolor. Cursus metus aliquam eleifend mi in. Volutpat commodo sed egestas egestas fringilla phasellus. Viverra adipiscing at in tellus integer feugiat scelerisque varius. Arcu bibendum at varius vel pharetra. Dictum at tempor commodo ullamcorper. Eu consequat ac felis donec et odio pellentesque diam volutpat. Pretium quam vulputate dignissim suspendisse in est. Et pharetra pharetra massa massa ultricies mi quis hendrerit dolor. Dolor morbi non arcu risus quis varius.

Maecenas volutpat blandit aliquam etiam erat velit. Quis imperdiet massa tincidunt nunc pulvinar. Placerat vestibulum lectus mauris ultrices eros in cursus turpis massa. Sodales ut etiam sit amet. Orci nulla pellentesque dignissim enim sit amet venenatis. Fusce ut placerat orci nulla pellentesque dignissim enim sit. Sollicitudin ac orci phasellus egestas tellus rutrum tellus. Enim eu turpis egestas pretium aenean pharetra magna ac placerat. Et malesuada fames ac turpis egestas. Integer quis auctor elit sed vulputate. Massa tempor nec feugiat nisl pretium.

------------------------------------

## Heading 1

CoLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Mi ipsum faucibus vitae aliquet nec ullamcorper sit amet. Scelerisque fermentum

### Heading 2

CoLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Mi ipsum faucibus vitae aliquet nec ullamcorper sit amet. Scelerisque fermentum dui faucibus in ornare quam viverra orci. Maecenas ultricies mi eget mauris pharetra. Tempor nec feugiat nisl pretium fusce id. In ante metus dictum at tempor commodo ullamcorper a. Nulla at volutpat diam ut venenatis tellus in. 

Quis hendrerit dolor magna eget est lorem ipsum dolor. Cursus metus aliquam eleifend mi in. Volutpat commodo sed egestas egestas fringilla phasellus. Viverra adipiscing at in tellus integer feugiat scelerisque varius. Arcu bibendum at varius vel pharetra. Dictum at tempor commodo ullamcorper. Eu consequat ac felis donec et odio pellentesque diam volutpat. Pretium quam vulputate dignissim suspendisse in est. Et pharetra pharetra massa massa ultricies mi quis hendrerit dolor. Dolor morbi non arcu risus quis varius.


### Heading 2

This section describes key concepts used in the content of the document.  If the concept requires a footnote, one should be inserted as follows:  Any defined term should be hyperlinked to its glossary definition (or at least bolded).

## Heading 1

Quis hendrerit dolor magna eget est lorem ipsum dolor. Cursus metus aliquam eleifend mi in. Volutpat commodo sed egestas egestas fringilla phasellus. Viverra adipiscing at in tellus integer feugiat scelerisque varius. Arcu bibendum at varius vel pharetra. Dictum at tempor commodo ullamcorper. Eu consequat ac felis donec et odio pellentesque diam volutpat. Pretium quam vulputate dignissim suspendisse in est. Et pharetra pharetra massa massa ultricies mi quis hendrerit dolor. Dolor morbi non arcu risus quis varius.

### Heading 2

Eu consequat ac felis donec et odio pellentesque diam volutpat. Pretium quam vulputate dignissim suspendisse in est. Et pharetra pharetra massa massa ultricies mi quis hendrerit dolor. Dolor morbi non arcu risus quis varius.


#### Heading 3

CoLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Mi ipsum faucibus vitae aliquet nec ullamcorper sit amet. Scelerisque fermentum dui faucibus in ornare quam viverra orci. Maecenas ultricies mi eget mauris pharetra. Tempor nec feugiat nisl pretium fusce id. In ante metus dictum at tempor commodo ullamcorper a. Nulla at volutpat diam ut venenatis tellus in.

##### Heading 4

Sodales ut etiam sit amet. Orci nulla pellentesque dignissim enim sit amet venenatis. Fusce ut placerat orci nulla pellentesque dignissim enim sit. Sollicitudin ac orci phasellus egestas tellus rutrum tellus. Enim eu turpis egestas pretium aenean pharetra magna ac placerat. Et malesuada fames ac turpis egestas. Integer quis auctor elit sed vulputate. Massa tempor nec feugiat nisl pretium.

## Figures, Bullets and Numbered Lists

### Figure

Arcu bibendum at varius vel pharetra. Dictum at tempor commodo ullamcorper. Eu consequat ac felis donec et odio pellentesque diam volutpat. Pretium quam vulputate dignissim suspendisse in est. Et pharetra pharetra massa massa ultricies mi quis hendrerit dolor. Dolor morbi non arcu risus quis varius


[image]: image.png "Image Title" 
![Alt text][image] 
A reference to the [image](#image).

### Figure 1. Mi ipsum faucibus vitae


### Lists

Eu consequat ac felis donec et odio pellentesque diam volutpat:

1. Establish Magna
    1. Dictum at tempor commodo
    1. Volutpat commodo sed,
        1. Cursus metus aliquam eleifend.


- Identify Bibendum,
   - Analyze Donec,
      - Treat Fringilla,

### Quote

The following is a quote from a referenced source:

> This is a quote from an author in a paper that provides invaluable insight into the subject of this ToIP document. Be sure to include a reference to the source.

### Conclusion

CoLorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Mi ipsum faucibus vitae aliquet nec ullamcorper sit amet. Scelerisque fermentum dui faucibus in ornare quam viverra orci. Maecenas ultricies mi eget mauris pharetra. Tempor nec feugiat nisl pretium fusce id. In ante metus dictum at tempor commodo ullamcorper a. Nulla at volutpat diam ut venenatis tellus in.

- This section seems incorrectly indented: https://github.com/trustoverip/specification-template/issues/1


[//]: # (Pandoc Formatting Macros)

[//]: # (# This is an annex {#sec:annexA .normative})

[//]: # (With some text)

[//]: # (# This is another annex {#sec:annexB .informative})

[//]: # (With some more text)

## Annex

Annex content

[//]: # (Pandoc Formatting Macros)

[//]: # (\newpage)

[//]: # (\makebibliography)

