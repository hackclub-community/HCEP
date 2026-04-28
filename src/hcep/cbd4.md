---
status: draft
type: Meta
dateCreated: 2026-04-16
dateReceived: 2026-04-28
discussionsTo: https://github.com/hackclub-community/meta/discussions/5
trackingIssue: https://github.com/hackclub-community/HCEP/issues/1
authors: Andrei Jiroh Halili <andreijiroh@alumni.hackclub.community>
hide: [navigation]
---

# HCEP-cbd4 - Hack Club Enhancement Proposals Process, Purpose and Guidelines

## Summary

A Hack Club Enhancement Proposal is a document that provides information to the Hack Club community. The goal of a HCEP is to improve Hack Club HQ and its community in different fronts, from community moderation and health to running YSWSes and other kind of programs and events and beyond.

This document describes the scope, format and process of publishing Hack Club Enhancement Proposals.

## Scope and Objectives

A Hack Club Enhancement Proposal (HCEP) should be a concise and focused documentation of a specific topic that is of interest to the Hack Club community.

A proposal should always have the intention of improving Hack Club’s programs, services and community.

Proposals may include descriptions of technical protocols and mechanisms, documentation of experimental work or current best practices.

Proposals are not limited to technical topics and may focus on social and cultural aspects.

Proposals may be entertaining and humorous (unlike this proposal).

## HCEP Types

There are 4 types (or tracks if we’re pedantic on IETF RFCs side) of HCEP, formed around the EIPs but specific for the Hack Club community:

* **Community Projects Operations** tackles the daily operations of running and managing community projects within Hack Club, from the community infrastructure (e.g. Nest or Coolify for self-hosting, Cloudflare for DNS, etc.)
* **Moderation and Community Health** describes proposals relating to how the Conduct WG (mostly formed through the Moderation community subteam, also known as the Fire Department in the Slack, and select HQ staff) moderate community spaces in scope with the Hack Club Code of Conduct
* **Meta** describes processes around Hack Club proposes a change to (or an event in) a process. Meta HCEPs include HQ and community policies codified as a Meta HCEP, governance and community team proposals, event/program proposal, and others that would help improve Hack Club as a whole.
* **Informational** describes proposals that would provide information for the community but it is either the authors’ commentary or is not legally binding.

The type is chosen by the author. If the type is not specified, the proposal is assumed to be informational.

Anyone can propose to amend this list by submitting a Meta HCEP for review by both the HCEP Maintainers and the wider community. Once approved, the list of HCEP Types will be updated accordingly.

## Language, Document Structure and Format

All Hack Club Enhancement Proposals must be written in English, be properly formatted as [CommonMark](https://spec.commonmark.org/0.29/) and/or [GitHub-Flavored Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) and be reasonably grammatical.

Authors should use inclusive language and examples and refrain from using [oppressive terminology](https://tools.ietf.org/html/draft-knodel-terminology) as part of following and embracing the hacker values under the [Hack Club Code of Conduct](https://hackclub.com/conduct).

### Proposal Title and Identifier

Every Hack Club Enhancement Proposal must have a descriptive title. If you still undecided on your proposal title, use `TBD0` as a temporary placeholder identifier until it get finalized.

An identifier is computed from the proposal title as the first 4 digits of the sha256 hash (in hex). The identifier can be computed from the title with standard Unix tools:

```bash
$ echo -n "Hack Club Enhancement Proposals Process, Purpose and Guidelines" | sha256sum | cut -c-4
cbd4
```

By using the hash of the title as identifier we reduce the burden on facilitators to assign unique IDs. This requires proposal titles to be unique.

In case of proposal title changes, the previous proposal ID must be marked as `Replaced with HCEP-XXXX due to title changes` in its status field and the new proposal title hash must be regenerated and used as its new ID moving forward.

### Metadata

Proposal metadata is placed at the top of the document as key-value pairs between opening and closing `---` in typical YAML fashion.

Following metadata key-value pairs may be placed at the top of a proposal:

* `type` - Indicates the type of the proposal
* `status`: Indicates the proposal status. Can be either `DRAFT`, `WITHDRAWN`, or `FINAL`.
* `dateReceived`: Date of when the proposal was added to the repository (when status is set to `DRAFT`).
* `dateWithdrawn`: Date of when the proposal status was set to `WITHDRAWN` (only for proposals with status `WITHDRAWN`).
* `dateFinalized`: Date of when the proposal status was set to `FINAL` (only for proposals with status `FINAL`).
* `trackingIssue`: Link to the tracking issue for the proposal in the HCEP repository.
* `discussionsTo`: Link to the discussion (either in the `#hceps` Slack channel or at the Hack Club community projects GitHub organization discussions’ [HCEP Discussions Threads](https://github.com/hackclub-community/meta/discussions/categories/hcep-discussion-threads)).
* `relatedHceps`: A YAML list or JSON array of related HCEPs (e.g. `[HCEP-cbd4, HCEP-9a23]`).
* `replaces`: A YAML list or JSON array of HCEPs that are replaced by the proposal.
* `replacedBy`: Identifier of a HCEP that replaces the proposal.
* `livingDocument`: Boolean that identifies a HCEP as a living document, mainly used by this HCEP and other codified documents such as HCEP-e332 (Hack Club Code of Conduct)

### Required Sections

Every HCEP should include at least the following sections:

* Summary: A short (no more than 200 words) summary of the proposal.
* Copyright: Indicating that the proposal has been placed in the public domain.
* Citation: Documenting how to cite the proposal when used, following EIP-styled citation formatting (see example below).

Following sections may be included in a proposal:

* History: An overview of previous related efforts and how they relate to the proposal. A subsection called **Prior art** can be also added
* Implementations: If applicable an overview of projects, services or applications that implement the proposal at time of submission.
* References: A list of documents and resources referenced by the proposal.

## The HCEP Process

1. A Hack Club Enhancement Proposal can be submitted by individuals or groups of individuals (authors) by submitting a patch to the HCEP repository. Submissions through the use of Slack canvas feature is permitted as long as it is for collaboratively working on a draft proposal and temperature checking with the community before formally submitting as a patch.
2. Within seven days one of the maintainers will read and respond to the proposal. The maintainer checks if the proposal conforms to the required structure and fits the scope and objective of the HCEPs. The maintainer may request the authors to clarify, justify, or withdraw the proposal. Such a request must not reflect the personal bias of a maintainer. Rather, it will be made strictly to maintain a high quality of submissions. The maintainers reserve the right to reject a submission when a proposal amounts to blatant misuse of the process. The authors may seek feedback from the wider community if the submitted proposal is rejected or clarifications are requested.
3. If a HCEP facilitator approves a submission it receives the status `DRAFT` and is added to the repository. The facilitator also creates a tracking issue for the proposal and adds `trackingIssue` attribute to the proposal metadata.
    
    1. Registered proposals must have the following metadata attributes: `slug`, `authors`, `status`, `dateReceived`, `trackingIssue` and `discussionsTo`.
    2. When the status is changed to `FINAL` or `WITHDRAWN`, facilitator adds `dateFinalized` or `dateWithdrawn` attributes to the proposal metadata.
4. While a proposal has the status `DRAFT`:
    
    1. Authors are responsible for initiating community discussion and collecting feedback.
    2. Authors may submit updates to the proposal which will be checked in to the repository by a maintainer. Others may also submit updates, but in this case a change must be approved by at least one author.
    3. Authors may withdraw the submission upon which a maintainer will set the status of the submission to `WITHDRAWN`.
5. After at least 60 days the authors may request the proposal to be finalized. This is done by requesting final comments on the proposal.
    
    1. If there are no community objections within 14 days and the authors can show that they have initiated sufficient awareness and discussion of the proposal, a facilitator will set the status of the submission to `FINAL`.
6. If authors have not requested the proposal to be finalized, and there were no updates for 2 years or longer, a facilitator will set the status of the submission to `WITHDRAWN`.
7. A proposal with status `FINAL` can not be changed or updated in a way that would lead to adjustments to implementations. Minor corrections are allowed.
8. Unless the HCEP is a living document, any substantial change to finalized proposal must be submitted as a separate HCEP.
    
    1. The new HCEP MUST include a `replaces` metadata attribute pointing to FEPs it supersedes.
    2. If the new HCEP becomes `FINAL`, the original one MUST point to it in an added `replacedBy` metadata attribute.
9. A proposal with status `WITHDRAWN` remains in the repository and can be resubmitted.
10. After a proposal becomes `FINAL` a maintainer will archive all discussions linked in the tracking issue and add the resulting archive links to the tracking issue. In case of living documents, it’s at the discretion of either the maintainers or HCEP authors to archive discussions linked in the tracking issue unless it is required for moderation reasons as requested by the Moderation community subteam/Fire Department.

### HCEP maintainers

A list of maintainers is maintained in the `src/maintainers.md` source file in the repository or at [https://hceps.hackclub.community/maintainers](https://hceps.hackclub.community/maintainers).

### HCEP Submission Methods

A list of methods in which a proposal may be submitted is maintained in the `src/submission.md` source file in the HCEP repository or at [https://hceps.hackclub.community/submission](https://hceps.hackclub.community/submission).

### HCEP governance

HCEP-cbd4 (Hack Club Enhancement Proposals Process, Purpose and Guidelines) is a living document and can be updated despite having the `FINAL` status.

Anyone can propose a change to HCEP-cbd4 (or other documents related to the HCEP process) using any method listed in HCEP submission methods section above. The change must be approved by at least two facilitators (one of them could be the submitter). For any part of the FEP process, there must be a sufficient number of facilitators who agreed to do the maintenance work. Changes should not be accepted before at least 1 month passes after the last update, to give facilitators and the community time to review them and provide feedback.

Minor changes (i.e. a correction of a typo or of a broken link) can be accepted immediately after getting two approvals from facilitators.

## Style Guide

### Proposal name and description

The proposal name should be in title case, should not include the word “standard” or any variation thereof, and should not include the HCEP’s identifier.

The proposal description follows similarly to the above but should be in sentence case.

### RFC 2119 and RFC 8174

HCEPs are encouraged to follow [RFC 2119](https://www.ietf.org/rfc/rfc2119.html) and [RFC 8174](https://www.ietf.org/rfc/rfc8174.html) for terminology and to insert the following at the beginning of the Specification section or similar sections as needed:

> The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “NOT RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119 and RFC 8174.

Don’t use RFC 2119 keywords (all-caps SHOULD/MUST/etc.) outside of the specification or similar section(s).

## History

Hack Club Enhancement Proposals was developed initially by Andrei Jiroh Halili as part of [community](https://hackclub.enterprise.slack.com/docs/T0266FRGM/F09TTD7V56E) [proposals](https://hackclub.enterprise.slack.com/docs/T0266FRGM/F09ULUP2XK3) on improving meta discussions around Hack Club both as a non-profit US-based organization and global online community by standardizing proposal processes and archiving them outside the Slack in the form of a Git repository for prosperity.

The process and format described in [FEP-a4ed](https://codeberg.org/fediverse/fep/src/branch/main/fep/a4ed/fep-a4ed.md) is influenced by other community driven documentation efforts such as the [BitTorrent Enhancement Proposal Process](http://bittorrent.org/beps/bep_0001.html), [Scheme Request for Implementation](https://srfi.schemers.org/srfi-process.html) and the [IETF RFC Series](https://www.rfc-editor.org/info/rfc8729).

[EIP-1](https://eips.ethereum.org/EIPS/eip-1) was derived heavily from [Bitcoin’s BIP-0001](https://github.com/bitcoin/bips) written by Amir Taaki which in turn was derived from [Python’s PEP-0001](https://peps.python.org/). In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Ethereum Improvement Process, and should not be bothered with technical questions specific to Ethereum or the EIP.

### Prior art

Portions of this HCEP are adopted from the following documents outside the Hack Club community, particularly:

* Martin Becze <[mb@ethereum.org](mailto:mb@ethereum.org)\>, Hudson Jameson <[hudson@ethereum.org](mailto:hudson@ethereum.org)\>, et al., "EIP-1: EIP Purpose and Guidelines," _Ethereum Improvement Proposals_, no. 1, October 2015. Available: [https://eips.ethereum.org/EIPS/eip-1](https://eips.ethereum.org/EIPS/eip-1).
* pukkamustard <[pukkamustard@posteo.net](https://mailto:pukkamustard@posteo.net)\>, “FEP-a4ed: The Fediverse Enhancement Proposal Process,” _Fediverse Enhancement Proposals_, October 2020. Available: [https://codeberg.org/fediverse/fep/src/branch/main/fep/a4ed/fep-a4ed.md](https://codeberg.org/fediverse/fep/src/branch/main/fep/a4ed/fep-a4ed.md)

## References

Alongside the standard prior art, these are the sources referenced throughout the HCEP (most of them are from FEP-a4ed):

* Dave Mason, [Scheme Request For Implementation - Process](https://srfi.schemers.org/srfi-process.html)
* David Harrison, [The BitTorrent Enhancement Proposal Process](http://bittorrent.org/beps/bep_0001.html), 2008
* Housley, R., Ed., and L. Daigle, Ed., [The RFC Series and RFC Editor](https://www.rfc-editor.org/info/rfc8729), 2020
* John MacFarlane, [CommonMark Spec Version 0.29](https://spec.commonmark.org/0.29/), 2019
* Mallory Knodel, [Terminology, Power and Oppressive Language](https://tools.ietf.org/html/draft-knodel-terminology)

## License

CC0 1.0 Universal (CC0 1.0) Public Domain Dedication

To the extent possible under law, the authors of this document, alongside contributors, have waived all copyright and related or neighboring rights to this work.

## Citation

Please cite this document as:

Andrei Jiroh Halili <andreijiroh@alumni.hackclub.community>, “HCEP-cb d4 - Hack Club Enhancement Proposals Process, Purpose and Guidelines," _Hack Club Enhancement Proposals_, April 2026. Available: https://hceps.hackclub.community/hcep/cbd4
