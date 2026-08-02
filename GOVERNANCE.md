# csi-rs Governance

This document describes how projects hosted under the **csi-rs** GitHub organization are governed, how decisions are made, and how responsibility is delegated.

## 1. Scope

The csi-rs project develops open-source Rust software for collecting, transporting, processing, storing, and visualizing Wi-Fi Channel State Information on ESP devices and host systems.

This governance policy applies to all repositories owned by the csi-rs organization unless a repository contains an approved supplementary governance document.

Repository-specific governance may define additional responsibilities, such as release managers or component owners, but it must not contradict this organization-wide policy.

## 2. Governance model

csi-rs follows a **Benevolent Dictator for Life (BDFL)** governance model.

The current BDFL is:

* **[Ammar] ([@stacks-of-data])**

The BDFL has final authority over the direction and governance of the project. In normal operation, however, decisions should be delegated to repository maintainers and reached through open discussion and consensus.

The term “for life” does not require the BDFL to serve permanently. The BDFL may resign, appoint a successor, become unable to serve, or be removed under the exceptional circumstances defined in this document.

## 3. Governance principles

Project decisions should follow these principles:

### Openness

Technical proposals, decisions, and their reasoning should normally be recorded in public issues, pull requests, discussions, or project documentation.

Security matters, conduct reports, personal information, and other sensitive matters may be handled privately.

### Technical merit

Decisions should be based on technical evidence, maintainability, compatibility, user impact, project scope, and the long-term health of the ecosystem.

### Consensus first

Maintainers should make a reasonable effort to understand objections and reach consensus before escalating a decision to the BDFL.

Consensus does not require unanimous agreement. It means that relevant concerns have been considered and no unresolved objection clearly outweighs the proposed benefit.

### Delegated ownership

The BDFL should not be required to approve routine work. Repository maintainers are trusted to make decisions within their assigned areas.

### Compatibility and reliability

Because csi-rs repositories form a connected embedded and host-side ecosystem, changes should consider compatibility across firmware, libraries, protocols, serialized data formats, servers, clients, supported hardware, and published crates.

### Community health

All participants, including maintainers and the BDFL, are subject to the project’s Code of Conduct.

## 4. Roles

### 4.1 Users

Users are people or organizations that use csi-rs software, documentation, hardware configurations, or published packages.

Users are encouraged to:

* Report defects and regressions.
* Propose improvements.
* Provide reproducible hardware and software information.
* Participate constructively in project discussions.

Using the software does not by itself grant project decision-making authority.

### 4.2 Contributors

A contributor is anyone who contributes to the project through code, documentation, testing, issue triage, design discussion, hardware validation, research, support, or other useful work.

Contributors may participate in decisions and reviews, but they do not have merge, release, or administrative authority unless those responsibilities have been explicitly delegated.

### 4.3 Maintainers

Maintainers are trusted contributors with responsibility for one or more repositories or project areas.

A maintainer may be authorized to:

* Triage issues and pull requests.
* Review and merge changes.
* Manage labels, milestones, and releases.
* Maintain documentation and examples.
* Publish packages or release artifacts.
* Define implementation details within their assigned area.
* Represent their repository in cross-repository decisions.

Maintainer authority is limited to the repositories and responsibilities assigned to them.

Maintainers are expected to:

* Exercise technical judgment in the project’s interest.
* Review contributions fairly and respectfully.
* Keep important decisions publicly documented.
* Protect project credentials, packages, and infrastructure.
* Identify conflicts of interest.
* Coordinate changes that affect other csi-rs repositories.
* Avoid creating unnecessary barriers for contributors.

Repository maintainers should be publicly identifiable through a repository README, `CODEOWNERS`, project documentation, or another organization-maintained list.

### 4.4 BDFL

The BDFL is the final decision-maker and principal steward of the csi-rs project.

The BDFL is responsible for:

* Maintaining the project’s overall vision and scope.
* Resolving decisions that cannot be settled through consensus.
* Appointing and removing maintainers.
* Delegating repository and release responsibilities.
* Approving organization-wide policy changes.
* Protecting the continuity, identity, and integrity of the project.
* Coordinating decisions that affect several repositories.
* Planning for succession and operational continuity.

The BDFL may overrule another project decision, but should do so rarely and provide a clear public explanation unless the matter is confidential.

The BDFL is not expected to review every contribution or control routine implementation details.

## 5. Decision-making process

### 5.1 Routine decisions

Routine decisions may be made by the maintainers responsible for the affected repository or component.

Examples include:

* Bug fixes that preserve intended behaviour.
* Documentation corrections.
* Test improvements.
* Internal refactoring without public compatibility consequences.
* Dependency updates that do not materially change supported platforms.
* Minor user-interface improvements.
* Patch releases.

These decisions normally occur through ordinary issue and pull-request review.

### 5.2 Substantial decisions

A substantial decision should be proposed publicly before implementation or merge.

Examples include:

* Breaking changes to a public Rust API.
* Changes to the device-to-host command protocol.
* Changes to serialized CSI or configuration formats.
* Removing support for an ESP chip, development board, or operating mode.
* Introducing a major dependency or runtime requirement.
* Splitting, merging, renaming, transferring, or archiving a repository.
* Creating a new official csi-rs repository.
* Changing licensing or package ownership.
* Making incompatible changes between firmware, server, and client releases.
* Changing release or compatibility policy.
* Modifying project governance.

A proposal should describe:

1. The problem being addressed.
2. The proposed solution.
3. Relevant alternatives.
4. Compatibility and migration effects.
5. Repositories and maintainers affected.
6. Testing or validation requirements.

The proposal should remain open for a reasonable comment period. For non-urgent organization-wide decisions, five calendar days is the normal minimum.

### 5.3 Consensus

Maintainers should attempt to reach consensus through technical discussion.

When consensus is reached, an authorized maintainer may record the outcome and proceed with implementation.

Silence alone should not be treated as strong approval when a decision has significant compatibility or governance consequences.

### 5.4 Escalation to the BDFL

When consensus cannot be reached within a reasonable period, a maintainer may request a BDFL decision.

Before deciding, the BDFL should:

1. Review the proposal and material objections.
2. Ask for clarification when necessary.
3. Consider effects across the complete csi-rs ecosystem.
4. Record the final decision and its reasoning.

The BDFL’s decision is final unless the BDFL later reopens the matter.

### 5.5 Urgent decisions

A maintainer or the BDFL may act without the normal discussion period when necessary to address:

* A security vulnerability.
* Compromised credentials or release infrastructure.
* A broken default branch or release.
* Data corruption.
* A severe hardware safety concern.
* A legal or licensing risk.
* A serious Code of Conduct incident.

The action and its reasoning should be documented afterward when disclosure is safe and appropriate.

## 6. Cross-repository changes

Changes that affect multiple repositories require coordination between the relevant maintainers.

A cross-repository proposal should identify:

* Every affected repository.
* The order in which changes and releases must occur.
* Compatible version combinations.
* Required migration instructions.
* Temporary compatibility measures, where applicable.
* The maintainer responsible for coordinating the work.

Particular care is required for changes affecting:

* `esp-csi-rs` and its core implementation.
* Firmware or command behaviour in `esp-csi-cli-rs`.
* Device-to-host framing and serialization.
* Webserver APIs and WebSocket behaviour.
* Parquet or exported data schemas.
* Desktop or embedded clients consuming those interfaces.
* Supported Espressif chips, boards, and toolchain versions.

A change should not knowingly leave the official repositories in an undocumented incompatible state.

## 7. Pull requests and merging

An authorized maintainer may merge a pull request when:

* The change is within project scope.
* Relevant review concerns have been addressed.
* Required tests and checks pass.
* Public behaviour is documented where necessary.
* Compatibility consequences are understood.
* The contribution complies with the Code of Conduct and contribution policy.

For substantial changes, the author should not be the only reviewer when another qualified maintainer is reasonably available.

Minor or urgent changes may be merged without a second reviewer when necessary. The maintainer remains responsible for the result.

BDFL approval is not required for ordinary pull requests.

## 8. Releases and project assets

Release authority may be delegated to designated maintainers.

Official project assets include:

* GitHub organizations and repositories.
* Published Rust crates and package namespaces.
* Release binaries and firmware images.
* Documentation hosting.
* Domains and project identities.
* CI/CD credentials and signing material.
* Security advisory access.
* Project communication accounts.

These assets must be managed for the benefit and continuity of the project rather than for the personal benefit of an individual maintainer.

Critical administrative access should, where practical, be held by at least two trusted project members.

Release managers must not publish incompatible or security-sensitive releases without coordinating with the relevant maintainers.

## 9. Becoming a maintainer

Maintainers are selected based on demonstrated trust rather than a fixed number of contributions.

Relevant considerations include:

* Sustained useful participation.
* Technical understanding of the relevant repository.
* Constructive review and communication.
* Respect for project scope and compatibility.
* Reliability in following through on responsibilities.
* Compliance with the Code of Conduct.
* Willingness and availability to perform maintenance work.

A current maintainer may nominate a contributor. The BDFL should consult the relevant maintainers before approving the appointment.

The new maintainer must accept the role and its responsibilities.

Administrative permissions should follow the principle of least privilege.

## 10. Inactivity, resignation, and removal

A maintainer may resign at any time.

A maintainer who expects to be unavailable for an extended period should notify the project when practical.

After approximately six months without project participation, the BDFL or another maintainer may ask whether the person wishes to remain active. If no response is received within a reasonable period, the person may be moved to emeritus status and unnecessary access may be removed.

Emeritus maintainers retain recognition for their contributions but have no automatic administrative authority.

A maintainer may be removed for:

* Serious or repeated Code of Conduct violations.
* Misuse of project access.
* Deliberately compromising project security or integrity.
* Persistent abuse of authority.
* Repeatedly acting against documented project decisions.
* Sustained inability to perform the role.

Except where immediate suspension is required to protect the project or community, the person should be informed of the concern and given an opportunity to respond.

The BDFL makes the final removal decision after consulting uninvolved maintainers.

## 11. Conflicts of interest

Project participants should disclose conflicts that could reasonably affect their judgment.

A maintainer should recuse themselves from deciding matters involving:

* Their own alleged misconduct.
* A direct financial or employment conflict.
* A personal dispute that prevents impartial review.
* A contribution whose approval would create a significant private benefit not shared by the project.

The BDFL is also subject to this requirement.

The BDFL may not personally control the handling of a Code of Conduct complaint made against the BDFL. Such a complaint must be handled by uninvolved maintainers or an agreed independent party.

## 12. BDFL succession

The BDFL may resign and appoint a successor after consulting active maintainers.

The successor should:

* Understand the technical and community scope of csi-rs.
* Have a demonstrated history of responsible project participation.
* Be trusted to delegate authority.
* Accept responsibility for project continuity.
* Publicly accept the role.

The BDFL may designate an acting or deputy BDFL for periods of temporary absence.

If the BDFL is unreachable or unable to serve for at least 90 days and has not designated an acting BDFL, the active maintainers may select an acting BDFL by a two-thirds majority.

If the BDFL permanently leaves without naming a successor, the active maintainers may select a new BDFL by a two-thirds majority. The decision and voting record should be documented publicly.

For this section, an active maintainer is a maintainer who has participated in project maintenance during the preceding six months or who is on an acknowledged temporary leave.

### Exceptional removal of the BDFL

The BDFL may be removed only in exceptional circumstances involving:

* Serious Code of Conduct violations.
* Deliberate misuse of project assets or credentials.
* A material threat to the security or continuity of the project.
* Sustained incapacity to perform the role.
* Persistent conduct that fundamentally violates this governance document.

Removal requires a two-thirds majority of active maintainers excluding the BDFL, with at least two maintainers supporting removal.

The reasons must be documented, subject to necessary privacy and security restrictions. The maintainers must then appoint an acting or permanent successor under the succession process above.

## 13. Forks and project freedom

All csi-rs software remains governed by the license of its respective repository.

Nothing in this governance document prevents anyone from using, modifying, or forking the software under those license terms.

The authority described in this document applies to the official csi-rs organization, repositories, packages, releases, and project identity. It does not grant control over independent forks.

## 14. Amendments

Any contributor may propose an amendment to this document through a public issue or pull request.

A governance amendment should normally remain open for comment for at least seven calendar days.

The BDFL approves organization-wide governance amendments after considering maintainer and community feedback.

Emergency temporary measures may be adopted immediately to protect the project, but they must be reviewed and either confirmed, revised, or withdrawn afterward.

---

**Adopted:** [2026-08-01]
**Current BDFL:** [Ammar] ([@stacks-of-data])
**Last amended:** [2026-08-01]
