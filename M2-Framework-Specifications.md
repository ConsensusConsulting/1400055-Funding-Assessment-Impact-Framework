# Cardano Funding Ecosystem - M2 Framework Specifications

**Report Date:** January 2026
**Version:** 2.4
**Prepared By:** Consensus Consulting LLC
**Report Type:** Framework Development (Milestone 2)
**Project:** Fund 14 Ecosystem Assessment (Project 1400055)

---

## Executive Summary

This document delivers the Milestone 2 (M2) framework specifications for the Cardano Funding Ecosystem Assessment project. Building on the diagnostic findings from Milestone 1, this document outlines strategic requirements to address the five gaps identified across Project Catalyst, BuilderDAO, and Intersect MBO.

The framework is informed by 11 stakeholder interviews conducted during M1, representing perspectives from Catalyst administration, Cardano Foundation, funded proposers, milestone reviewers, and ecosystem builders. A consistent theme emerged across these conversations: while the three funding mechanisms serve complementary purposes, they operate in isolation without shared infrastructure for tracking projects, identifying builders, or coordinating strategy.

**Framework Components:**

| Component | Purpose | M1 Gap Addressed |
| :---- | :---- | :---- |
| Impact Measurement Framework | Standardized outcome measurement across mechanisms | Accountability Variation Gap |
| Builder Profile Architecture | Cross-program identity and achievement tracking | Data Sharing Gap |
| Coordination Infrastructure | Phased approach to mechanism alignment | Coordination Gap |
| Technical Integration Requirements | Unified Project Tracking System specifications | Data Sharing Gap, Strategic Alignment Gap |

**Scope Clarification:** This framework establishes strategic requirements and architectural direction for implementation. It provides specifications detailed enough for technical teams to begin build work without additional consulting. Detailed technical specifications (database schemas, API endpoint design, smart contract logic) should be developed by qualified implementation teams during the build phase.

The full M1 Diagnostic Report is available at: [https://hackmd.io/2NeKIbn2RKWIsIGKk1K5TQ](https://hackmd.io/2NeKIbn2RKWIsIGKk1K5TQ)

---

## Table of Contents

1. [Project Background](#1-project-background)
2. [M1 Gap Summary and Stakeholder Context](#2-m1-gap-summary-and-stakeholder-context)
3. [Impact Measurement Framework](#3-impact-measurement-framework)
4. [Coordination Infrastructure](#4-coordination-infrastructure)
5. [Builder Profile Architecture](#5-builder-profile-architecture)
6. [Technical Integration Requirements](#6-technical-integration-requirements)
7. [Assessment of Existing Tools](#7-assessment-of-existing-tools)
8. [Governance Metadata Extension Requirements](#8-governance-metadata-extension-requirements)
9. [Gap Coverage Matrix](#9-gap-coverage-matrix)
10. [Stakeholder Validation Summary](#10-stakeholder-validation-summary)
11. [Evidence of Milestone Completion](#11-evidence-of-milestone-completion)
12. [References](#12-references)

---

## 1. Project Background

This project is a four-month assessment of the Cardano funding ecosystem, commissioned through Project Catalyst Fund 14. The analysis covers three primary funding mechanisms representing approximately $278.7M in ecosystem funding:

| Mechanism | Allocation | Projects | Primary Focus |
| :---- | :---- | :---- | :---- |
| Project Catalyst | ~$140.7M (₳204.6M + $38.4M) | 2,222 | Early-stage innovation |
| BuilderDAO | ~$6M (₳12M) | 20 funded | Growth-stage builders |
| Intersect MBO | ~$132M (₳264M) | 37 programs | Core infrastructure |

**Source:** Catalyst Public Reporting Tracker [\[1\]](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/), Intersect Budget Documentation [\[2\]](https://committees.docs.intersectmbo.org/intersect-budget-committee/archive/2025-cardano-budget-proposal-a-cardano-blockchain-ecosystem-budget), BuilderDAO Governance [\[3\]](https://medium.com/tap-in-with-taptools/cb-dao-projects-funded-c0b3d3bd531f)

Milestone 1 delivered a diagnostic assessment, including stakeholder mapping, process documentation, and a gap analysis, based on primary research and stakeholder interviews. This Milestone 2 report builds on those findings by outlining prescriptive framework requirements that address each identified gap.

---

## 2. M1 Gap Summary and Stakeholder Context

### Five Core Gaps

The M1 Diagnostic Report identified five structural gaps in the funding ecosystem:

**Gap 1: Coordination Gap**

No joint coordination body exists across the three mechanisms. BuilderDAO maintains unilateral rules referencing Catalyst (membership prerequisites and anti-double-dipping provisions), but no bilateral or trilateral structure supports strategic alignment or systematic information sharing.

Stakeholder interviews reinforced this finding. Interviewees described discovering redundant projects only through chance encounters. One example surfaced of multiple funded calendar projects where none of the teams knew the others existed. Developers in different regions frequently work on similar solutions without awareness of parallel efforts due to geographic and linguistic barriers.

**Gap 2: Data Sharing Gap**

Project data is fragmented across separate systems. Catalyst uses a Google Sheet tracker, BuilderDAO uses a  dashboard, and Intersect maintains committee documentation. No unified database enables cross-mechanism queries.

This emerged as a universal concern in stakeholder interviews. One interviewee identified "the lack of a unified data experience that connects the full journey a proposer and voter goes through" as the ecosystem's biggest gap. Another noted that no platform tracks proposal fulfillment "in a concise and accessible fashion." A third confirmed there is "no aggregated view across Catalyst, BuilderDAO, and Intersect."

**Gap 3: Strategic Alignment Gap**

No ecosystem-wide funding strategy exists that defines complementary roles, priorities, and shared success metrics. While stakeholders understand informally that Catalyst serves early-stage innovation, BuilderDAO supports growth, and Intersect funds infrastructure, no formal document establishes these roles.

Interviews revealed this as a deeper problem than structural documentation. Multiple stakeholders noted the absence of a shared "North Star" guiding funding decisions. One interviewee observed that asking ten different people what Catalyst is trying to achieve produces ten different answers. The Product Committee's Vision 2030 represents one attempt to address this, but no commonly agreed framework links the three mechanisms.

**Gap 4: Accountability Variation Gap**

Completion rates range from 67.5% (Catalyst overall) to 96% (Intersect quarterly milestones), with confounding variables making direct comparison difficult. More fundamentally, stakeholders questioned whether completion metrics measure the right things.

This concern appeared consistently across interviews. One interviewee explained that the current system assesses whether projects delivered on their promises, not whether that output created actual value. Another stated that "nobody is currently being held accountable for outcomes," and that the relationship between distributed funding and returned value remains opaque. Multiple interviewees noted the absence of post-funding tracking: no mechanism to assess whether projects remain operational six months after closeout.

**Gap 5: Geographic Concentration Gap**

Approximately 75% of funding flows to Western regions (North America and Europe). Analysis suggests this reflects application patterns rather than approval bias, but without systematic tracking infrastructure, the ecosystem cannot measure whether interventions are working.

### Stakeholder-Identified Themes

Beyond the five structural gaps, stakeholder interviews surfaced additional themes that informed the framework design:

**Voting Produces Popularity Contests Rather Than Merit-Based Selection**

Multiple interviewees described funding decisions driven by recognition rather than proposal quality. One stated that the system operates "fundamentally as a system driven by brand recognition and awareness rather than proposal merit." Voting patterns follow familiarity, and as a result, the same teams tend to win systematically while new ecosystem entrants with no established reputations are crowded out.

**Process Barriers Exclude Traditional Organizations**

Several interviewees highlighted difficulties onboarding organizations unfamiliar with cryptocurrency. Without intermediaries to navigate the process, traditional companies face impossible barriers. Documentation assumes participants already have Web3 knowledge. Payment in ADA makes budgeting difficult due to price volatility, where a budget could be worth ten thousand or a hundred thousand dollars depending on market conditions.

**Measurement Focuses on Outputs, Not Outcomes**

A universal critique centered on the disconnect between milestone completion and value creation. One interviewee noted that whether a project paints walls blue or develops a major ecosystem application makes no difference to the evaluation framework. Milestone fund allocations often don't correlate with actual effort. A six-month development phase might receive the same percentage as a two-minute closing video.

**Continuity Gaps Leave Successful Projects Unfunded**

Projects that complete initial work often cannot secure follow-on funding, leaving partial work abandoned. Mission-critical infrastructure competes in the same process as experimental projects. Relying on Catalyst for operational overhead is not viable because bureaucratic cycles cause inconsistent cash flow.

These themes informed the framework's emphasis on tiered accountability (proportional to grant size and project maturity), builder identity (enabling verification of track record), and coordination infrastructure (preventing duplication while enabling strategic progression).

---

## 3. Impact Measurement Framework

### Introduction and Purpose

M1 identified that completion rates vary significantly across mechanisms, with no standardized definition of "completed" or comparable impact metrics. Stakeholder interviews reinforced this finding. Interviewees consistently noted that the ecosystem measures whether projects delivered outputs, not whether those outputs created value.

The Impact Measurement Framework (IMF) addresses this through a unified approach to measuring and comparing project outcomes. The framework recognizes that a $5,000 micro-grant and a $3 million infrastructure program require different accountability approaches. It is built on three pillars: Strategic Alignment, Tiered Accountability, and Verifiable Proof.

### Strategic Alignment: Standardized Impact Categories

To enable ecosystem-wide portfolio analysis and ensure funding aligns with community priorities, the framework establishes four Impact Categories that all funded projects should map to:

| Impact Category | Definition | Aligned Mechanisms |
| :---- | :---- | :---- |
| **Core Infrastructure** | Projects that maintain, secure, or improve the base protocol and essential services. Examples include node tooling, block explorers, protocol upgrades, security audits. | Intersect MBO, Large Catalyst Grants |
| **Ecosystem Adoption** | Projects that drive user growth, on-chain activity, and utility. Examples include DeFi protocols, wallets, marketplaces, and developer SDKs. | BuilderDAO, Mid-Range Catalyst Grants |
| **Community & Governance** | Projects that enhance engagement, education, or governance processes. Examples include educational content, governance tooling, community programs. | Catalyst Grants, Governance Initiatives |
| **Research & Innovation** | Early-stage R&D, technical standards, and experimental concepts. Examples include academic research, CIP development, and proof-of-concept projects. | Catalyst Grants, Micro-Grants |

These categories emerged from analysis of how the mechanisms actually function. Intersect's budget explicitly allocates to infrastructure and research [\[2\]](https://committees.docs.intersectmbo.org/intersect-budget-committee/archive/2025-cardano-budget-proposal-a-cardano-blockchain-ecosystem-budget). BuilderDAO's KPI dashboard focuses on adoption metrics [\[4\]](https://cbdao.taptools.io/). Catalyst's challenge categories span all four areas [\[5\]](https://projectcatalyst.io/funds). The framework formalizes distinctions the ecosystem already makes informally.

**Category Assignment Process:**

1. **Proposer Selection:** At submission, proposers select a Primary Impact Category (and optionally a Secondary Category) with a brief rationale explaining the selection.
2. **Reviewer Validation:** During assessment, reviewers evaluate category fit. If reviewers recommend a different category, they document the rationale.
3. **Proposer Response:** If a change is recommended, proposers may either accept it or provide a counter-rationale.
4. **Mechanism Decision:** The funding mechanism determines the outcome, which is recorded in project tracking.

**Handling Ambiguous Cases:**

| Project Type | Category Guidance |
| :---- | :---- |
| Developer tooling | Core Infrastructure if supporting protocol operations; Research & Innovation if enabling new development patterns |
| DeFi protocols | Ecosystem Adoption (primary function drives on-chain activity); Core Infrastructure if providing services used by other projects |
| Educational content | Community & Governance if governance-focused; Research & Innovation if technically-focused for developers |
| Marketing and outreach | Ecosystem Adoption if measured by user growth; Community & Governance if focused on community building |

### Tiered Accountability: Proportional Requirements

Stakeholder interviews consistently emphasized that accountability rigor should match project maturity. Interviewees noted that being overly rigorous with quantifiable metrics must align with the maturity level of the recipients. Others observed that verification costs become prohibitive when applied uniformly. The cost to verify a $5,000 grant shouldn't approach the grant's value, while a $3 million infrastructure investment warrants thorough independent review.

The framework addresses this through tiered accountability, with requirements that scale with grant size:

**Tier 1: Universal Metrics (All Projects)**

All projects, regardless of size, should track basic information enabling cross-mechanism visibility:

- Unique project identifier
- Builder identity (linked to Stake Key)
- Impact Category assignment
- Funding mechanism source
- Project status (active, completed, discontinued)
- Total funding amount

**Tier 2: Maturity-Specific Metrics**

Additional metrics vary based on funding level:

| Funding Level | Typical Range | Focus | Example Metrics |
| :---- | :---- | :---- | :---- |
| Micro-Grant | < ₳10,000 | Technical output | Code commits, documentation published, prototypes delivered |
| Growth | ₳10,000 - ₳500,000 | Adoption & utility | Monthly active users, on-chain transactions, API usage, downloads |
| Infrastructure | > ₳500,000 | Ecosystem health | Total value locked, integration count, uptime, security audits |

### Verification Protocol

Verification rigor should scale with grant size. This addresses stakeholder concerns about both insufficient accountability for large grants and excessive burden for small experiments.

**Micro-Grants (< ₳10,000):**

- **Method:** Self-attestation with periodic random audit
- **Process:** Builder submits completion report with links to evidence. A percentage of completed micro-grants are randomly selected for audit each quarter.
- **Rationale:** Heavy verification would cost more than the grants themselves. Random audits create accountability without excessive overhead.

**Growth Tier (₳10,000 - ₳500,000):**

- **Method:** Milestone review with metric sampling
- **Process:** Each milestone must be reviewed before attestation. Reviewers confirm deliverables are complete. For quantitative metrics, reviewers verify the methodology and perform spot checks against independent data sources.
- **Rationale:** Significant investment justifies meaningful verification without auditing every data point.

**Infrastructure Tier (> ₳500,000):**

- **Method:** Third-party audit required
- **Process:** Projects engage approved third-party auditors to verify milestones. Auditors verify metrics against primary data sources. Reports are published alongside attestations.
- **Rationale:** Large investments justify thorough independent verification.

**Shared Verification Service:**

To reduce burden on individual mechanisms and ensure consistent standards, the framework proposes a shared Verification Service operating under Coordination Committee oversight:

| Function | Description |
| :---- | :---- |
| Micro-grant audits | Conduct random audits of self-attestations |
| Growth-tier support | Provide milestone review support for mechanisms |
| Auditor list | Maintain the approved auditor registry for infrastructure projects |
| Dispute investigation | Investigate complaints about attestation accuracy |

---

## 4. Coordination Infrastructure

### Introduction and Purpose

The M1 report documented that no joint coordination body exists across the three mechanisms. There is no bilateral information sharing, no cross-mechanism review processes, no forum for strategic discussion. Stakeholder interviews reinforced this finding with concrete examples of duplication and missed coordination opportunities.

The following three-phase approach builds coordination capacity incrementally, reducing political resistance while establishing the foundation for meaningful collaboration. Each phase builds on demonstrated value before requesting additional structure.

### Phase 1: Liaison Roles (Months 1-3)

Each funding mechanism designates one official liaison responsible for cross-mechanism awareness.

**Liaison Responsibilities:**

The Catalyst Liaison attends BuilderDAO governance calls [\[6\]](https://www.clarity.vote/organizations/cardano/CardanoBuilderDAO/governance/polls/-OT72kBXF1fXVdd25HPD) and Intersect committee meetings [\[7\]](https://www.intersectmbo.org/committees) as an observer. They report back to Catalyst leadership on funding priorities, approved projects, and potential overlaps. They maintain shared documentation tracking projects that have received or applied for funding across mechanisms.

The BuilderDAO Liaison attends Catalyst town halls and Intersect committee meetings. They flag potential duplication when members submit proposals covering work funded elsewhere. They share BuilderDAO's KPI methodology with other mechanisms.

The Intersect Liaison attends Catalyst and BuilderDAO governance sessions. They communicate Intersect's annual budget priorities [\[2\]](https://committees.docs.intersectmbo.org/intersect-budget-committee/archive/2025-cardano-budget-proposal-a-cardano-blockchain-ecosystem-budget) to other mechanisms. They identify opportunities for Intersect-funded infrastructure to support Catalyst and BuilderDAO operations.

**Implementation:**

- Each mechanism formally designates a liaison within 60 days of framework adoption
- Liaisons receive a small stipend from their respective mechanisms
- Liaisons publish monthly cross-mechanism briefings summarizing activities and coordination opportunities

**Success Criteria:**

- All three liaisons designated and active within 90 days
- At least 6 cross-mechanism briefings published in first year
- At least 3 documented instances of duplication prevention or coordination improvement

### Phase 2: Ecosystem Funding Strategy (Months 6-12)

Once liaison roles establish informal coordination, the ecosystem formalizes strategic alignment through an annual planning process.

**Annual Ecosystem Funding Strategy Process:**

In Q3 each year, liaisons collaborate to draft an Ecosystem Funding Strategy document that:

- Defines complementary roles of each mechanism for the coming year
- Identifies priority funding areas and gaps
- Establishes shared success metrics for ecosystem-wide impact
- Documents coordination protocols and dispute resolution procedures

The draft strategy is published for a 30-day community comment period. Liaisons incorporate feedback and finalize the document. The finalized strategy is submitted as a DRep Governance Action for ratification.

**What Ratification Means:**

Approval creates a public commitment to strategic alignment. Mechanisms that diverge from the strategy publish a rationale explaining the divergence. The strategy does not mandate specific funding decisions by any mechanism. It provides a coordination framework, not governance authority.

**Success Criteria:**

- First Ecosystem Funding Strategy published and ratified by Q4 2026
- All three mechanisms publicly commit to the strategy or publish divergence rationales
- Community feedback process generates meaningful engagement

### Phase 3: Formal Coordination Committee (Months 12-18)

After proving coordination value through Phases 1 and 2, the ecosystem establishes a formal Ecosystem Funding Coordination Committee.

**Committee Composition (9 voting members):**

| Seats | Source | Selection Method |
| :---- | :---- | :---- |
| 2 | Catalyst | 1 administration, 1 community-elected |
| 2 | BuilderDAO | 1 Board member, 1 member project-elected |
| 3 | Intersect | 1 Steering Committee [\[8\]](https://steeringcommittee.docs.intersectmbo.org/about/committee-members), 1 Budget Committee, 1 Technical Steering Committee |
| 2 | DRep Community | Elected through Intersect infrastructure [\[9\]](https://www.intersectmbo.org/news/intersect-committee-election-october-2025-results) |

**Committee Mandate:**

The committee's authority is explicitly advisory. It has no veto power over any mechanism's funding decisions.

Core functions:

- Maintain the annual Ecosystem Funding Strategy
- Identify and flag potential duplication across mechanisms
- Publish quarterly coordination reports with ecosystem-wide funding statistics
- Recommend policy changes to individual mechanisms (non-binding)
- Oversee the Unified Project Tracking System

**Committee Limitations:**

The committee cannot:

- Approve or reject funding proposals
- Reallocate funds between mechanisms
- Mandate policy changes
- Override mechanism-specific governance processes

These limitations preserve mechanism sovereignty while enabling coordination.

**Committee Operations:**

- Monthly meetings with public minutes published within 7 days
- Decisions require a simple majority (5 of 9 votes)
- One-year terms with staggered elections for continuity
- Funded through Intersect annual budget

---

## 5. Builder Profile Architecture

### Introduction and Purpose

M1 identified a "Builder Visibility Gap" where a builder's track record is siloed within each funding mechanism. A builder who successfully delivers Catalyst projects has no portable proof of that track record when applying to BuilderDAO.

Stakeholder interviews surfaced this concern repeatedly. Interviewees noted that the current system "recognizes time and popularity in the ecosystem rather than tangible impact." Others observed that winning requires "building significant community presence beforehand" since there is no other mechanism to establish credibility through demonstrated delivery. The result is that established teams with strong networks benefit from recognition, while newcomers cannot access the same consideration regardless of their actual capabilities.

The Builder Profile addresses this by creating a unified view of builder activity across all mechanisms, anchored to Cardano's existing Stake Key infrastructure.

### Identity Foundation: The Stake Key

The framework anchors builder identity to the Cardano Stake Key (`stake1...`) rather than proposing new identity infrastructure. This choice is strategic.

**Why Stake Keys:**

The Stake Key is universal. Every Cardano wallet user has one. It is non-custodial, so builders control their own identity. It is already used for governance: DRep registration, Catalyst voting, and delegation all use Stake Keys. It is persistent. Unlike payment addresses that can change, Stake Keys remain constant for a wallet. Existing tools already support it. GovTools [\[10\]](https://gov.tools/), explorers, and analytics platforms index by Stake Key.

**Technical Foundation:**

Stake Keys are defined in CIP-11 (Staking Key Chain for HD Wallets) [\[11\]](https://cips.cardano.org/cip/CIP-11) and CIP-19 (Cardano Addresses) [\[12\]](https://cips.cardano.org/cip/CIP-19). The stake address uses Bech32 encoding with the `stake1` prefix (mainnet) or `stake_test1` prefix (testnet). Multiple payment addresses can share the same Stake Key, making it a wallet-level identifier that persists across address changes.

**Implementation Approach:**

The builder's Stake Key should index all funding records across all mechanisms. This enables cross-mechanism queries ("show me all projects from this builder"), reputation aggregation across funding sources, and verification of builder identity through a cryptographic signature.

### Achievement Tracking

Builder achievements are tracked through attestations linked to the Builder's Stake Key.

**What Gets Tracked:**

- Project funding approvals (mechanism, amount, date)
- Milestone completions (verified by funding mechanism)
- Governance participation (DRep registration, voting activity)
- Cross-mechanism funding history

**Who Issues Attestations:**

The accountability body of each funding mechanism issues attestations:

- Catalyst: Milestone reviewers or audit processes
- BuilderDAO: DAO governance verification
- Intersect: Committee milestone verification

**Attestation Structure:**

Each attestation should include a reference to the builder's Stake Key, a hash of the detailed milestone/completion report, the identifier of the issuing mechanism, and the verification timestamp. This creates a verifiable record without storing sensitive details on-chain.

### Reputation Visibility

The Builder Profile aggregates verified achievements into a unified view. This section describes a conceptual model for community discussion. Specific weights and algorithms should be determined through community governance.

**Potential Reputation Components:**

| Component | What It Measures | Purpose |
| :---- | :---- | :---- |
| Completion Rate | Percentage of funded milestones completed | Rewards consistent delivery |
| Impact Score | Aggregated Tier 2 metrics normalized by grant size | Rewards measurable outcomes |
| Governance Activity | DRep participation, voting, and community contribution | Rewards ecosystem engagement |
| Funding Diversity | Number of mechanisms with successful completions | Rewards ecosystem breadth |

**Transparency Requirements:**

Any reputation algorithm should be publicly documented and version-controlled, subject to community governance for changes, and transparent to builders who can view component breakdowns.

The framework recommends transparency over opaque scoring. Show the builder's completion rate, verified metrics, and governance participation. Let reviewers and voters interpret the evidence rather than reducing it to a single number that obscures its derivation.

### Integration with Cardano Identity Standards

The Builder Profile should align with Cardano's existing governance metadata standards, particularly CIP-100 (Governance Metadata) [\[13\]](https://cips.cardano.org/cip/CIP-100) and CIP-119 (DRep Metadata) [\[14\]](https://cips.cardano.org/cip/CIP-119).

**Proposed Approach:**

On-chain anchor: A transaction signed by the Builder's Stake Key registers the profile, which contains the builder's Stake Key (identifier), URL to the off-chain profile document, the profile document hash (integrity verification), and the version identifier.

Off-chain profile: A JSON document following CIP-100 patterns containing builder description, achievement history, and URL to retrieve attestation history from the UPTS.

Tool integration: Platforms such as GovTools [\[10\]](https://gov.tools/) could display Builder Profile information alongside DRep profiles, providing unified identity visibility.

---

## 6. Technical Integration Requirements

### Introduction and Purpose

M1 identified a critical Data Sharing Gap. Project data is fragmented across Google Sheets, dashboards, and internal documents. Stakeholder interviews confirmed this as a universal concern. Interviewees described needing a "unified data experience that connects the full journey a proposer and voter goes through." Others noted the absence of any platform that tracks proposal fulfillment in an accessible way.

This section defines requirements for a Unified Project Tracking System (UPTS) that creates a single source of truth for all treasury-funded projects.

**Scope Note:** This framework establishes strategic requirements and architectural direction. Detailed technical specifications (database schemas, API endpoint design, authentication mechanisms) should be developed by qualified implementation teams during the build phase.

### UPTS Functional Requirements

The UPTS aggregates project data from all three funding mechanisms into a unified layer enabling cross-mechanism queries and analysis. It does not replace existing tools. Each mechanism continues using its preferred tracking systems while contributing data to the unified layer.

**Core Data Requirements:**

For each project:

| Data Element | Purpose |
| :---- | :---- |
| Unique project identifier | Cross-reference across systems |
| Builder identity (Stake Key) | Enable cross-mechanism queries |
| Project name and description | Human-readable identification |
| Funding mechanism source | Track which mechanism funded |
| Impact Category | Enable portfolio analysis |
| Funding amount (requested/distributed) | Financial tracking |
| Project status | Active, completed, discontinued |
| Milestone status | Progress tracking |
| Start/end dates | Timeline tracking |
| Link to full proposal | Reference to details |

For each milestone:

| Data Element | Purpose |
| :---- | :---- |
| Milestone identifier | Reference |
| Verification status | Pending, verified, failed |
| Attestation reference | Link to on-chain proof |
| Relevant Tier 2 metrics | Outcome measurement |

### UPTS Governance and Ownership

The UPTS is specified as a community-owned public good with a clear governance structure.

**Funding:**

The UPTS should be funded as a dedicated line item in Intersect's annual budget [\[2\]](https://committees.docs.intersectmbo.org/intersect-budget-committee/archive/2025-cardano-budget-proposal-a-cardano-blockchain-ecosystem-budget). This is appropriate because Intersect's mandate includes ecosystem coordination and infrastructure. They already manage similar public goods (GovTools, documentation). Budget Committee review ensures financial accountability. DRep approval provides democratic legitimacy.

**Stewardship:**

Intersect serves as the initial steward with defined responsibilities: host and maintain the infrastructure, implement updates approved by the Coordination Committee, provide technical support for integration mechanisms, and publish quarterly transparency reports.

Stewardship limitations: Cannot unilaterally modify data schema without Committee approval. Cannot restrict API access to any treasury-funded mechanism. Cannot use data for purposes beyond the stated scope without governance approval.

Stewardship should be reviewed after two years, with options to continue with Intersect, transition to a different steward, or establish a dedicated governance structure.

**Mandatory Integration:**

For the UPTS to be effective, all treasury-funded mechanisms should submit project data. This mandate requires a DRep Governance Action; it cannot be established by a technical specification alone.

Suggested governance action language: "All funding mechanisms receiving allocations from the Cardano Treasury submit project data to the Unified Project Tracking System within 30 days of project approval and update milestone status within 14 days of milestone completion."

### Integration Pathways

**Data Sources (Mechanisms → UPTS):**

| Mechanism | Current System | Integration Path |
| :---- | :---- | :---- |
| Project Catalyst | Milestone Module [\[15\]](https://milestones.projectcatalyst.io/) | API integration or data export; add Stake Key indexing |
| BuilderDAO | Clarity Platform [\[6\]](https://www.clarity.vote/organizations/cardano/CardanoBuilderDAO/governance/polls/-OT72kBXF1fXVdd25HPD), TapTools [\[4\]](https://cbdao.taptools.io/) | API push on approval/completion |
| Intersect | Committee documentation | Structured data submission process |

**Data Consumers (UPTS → Tools):**

| Tool | Integration Value |
| :---- | :---- |
| GovTools [\[10\]](https://gov.tools/) | Display Builder Profile alongside DRep profile |
| TapTools [\[16\]](https://www.taptools.io/) | Enrich analytics with funding history |
| Analytics platforms | Ecosystem-wide funding analysis |

### UPTS Public API Requirements

The UPTS should expose a public, read-only API enabling ecosystem tools to access unified data.

**Required Capabilities:**

| Capability | Description |
| :---- | :---- |
| Project listing | Retrieve all projects with filtering by status, Impact Category, and mechanism |
| Single project view | Retrieve the complete record for one project |
| Builder history | Retrieve all projects and attestations for a Stake Key |
| Impact aggregation | Retrieve aggregated metrics by Impact Category |

**Access Levels:**

| Level | Scope |
| :---- | :---- |
| Public read | Anyone can query project listings, builder histories, and aggregated metrics |
| Mechanism write | Authorized representatives submit/update records |
| Administrative | Technical staff for maintenance (with audit logging) |

---

## 7. Assessment of Existing Tools

This section assesses four existing ecosystem tools for their potential to integrate with the proposed framework.

### Catalyst Milestone Module

**Overview:** The Milestone Module [\[15\]](https://milestones.projectcatalyst.io/) is the official tracking system for Catalyst-funded projects, default since Fund 10. It implements structured reporting through Statements of Milestones (SoM) and Proofs of Achievement (PoA), with reviewer verification before payment release.

**Strengths:**

- Established infrastructure with historical data
- Structured reporting framework aligned with the framework's attestation model
- Integration with Catalyst funding workflow

**Limitations:**

- Catalyst-only; no cross-mechanism visibility
- Currently indexed by proposer name, not Stake Key
- Limited API access for external tools

**Integration Feasibility:** HIGH. Primary changes required: add a Stake Key to project records, develop an API or export for UPTS synchronization, and incorporate Impact Category assignment.

### BuilderDAO KPI Dashboard (TapTools)

**Overview:** TapTools [\[16\]](https://www.taptools.io/) provides the analytics infrastructure behind BuilderDAO's KPI dashboard [\[4\]](https://cbdao.taptools.io/). Their public API [\[17\]](https://openapi.taptools.io/) is well-documented and designed for integration.

**Strengths:**

- Real-time on-chain data integration
- KPI methodology aligned with the framework's Tier 2 metrics
- Well-documented API enables integration
- Proven methodology for measuring project impact

**Limitations:**

- BuilderDAO-focused; no cross-mechanism data
- Less applicable to research or community projects without measurable on-chain footprints

**Integration Feasibility:** HIGH. TapTools' KPI methodology informs the framework's growth-tier metrics. The API could feed adoption metrics directly to the UPTS for projects with on-chain activity.

### GovTools

**Overview:** GovTools [\[10\]](https://gov.tools/) is the official governance interface maintained by Intersect that implements CIP-1694 governance features. Documentation available at [\[18\]](https://docs.gov.tools/).

**Strengths:**

- Already uses Stake Key as identity anchor
- Implements CIP-100/119 metadata standards
- Open source enabling customization
- High ecosystem visibility for governance participation
- Maintained by Intersect

**Limitations:**

- Governance-focused, not project tracking
- No current support for builder funding history

**Integration Feasibility:** VERY HIGH. GovTools is the natural home for Builder Profile visibility. Integration involves extending profile display to include funding history by querying the UPTS API for the builder's project portfolio.

### Clarity Protocol

**Overview:** Clarity [\[19\]](https://www.clarity.community/) provides DAO governance infrastructure that BuilderDAO uses for voting and treasury management [\[6\]](https://www.clarity.vote/organizations/cardano/CardanoBuilderDAO/governance/polls/-OT72kBXF1fXVdd25HPD). Smart contract-enforced operations create verifiable on-chain records.

**Strengths:**

- Smart contract-enforced treasury operations
- Flexible voting options (linear, quadratic)
- Developer SDK for integration
- Proven with BuilderDAO's ₳12M governance

**Limitations:**

- DAO-focused; requires project structuring as DAO
- May be more infrastructure than needed for individual grantees

**Integration Feasibility:** HIGH for mechanism-level integration. Clarity serves as BuilderDAO's data source. Approved projects trigger data submission to UPTS, with on-chain records verifying funding.

### Integration Summary

| Tool | Primary Value |
| :---- | :---- |
| GovTools | Builder Profile display, Stake Key identity |
| TapTools | Tier 2 metric collection for growth projects |
| Catalyst Milestone Module | Catalyst project data source |
| Clarity | BuilderDAO data source |

---

## 8. Governance Metadata Extension Requirements

### Purpose

This section describes requirements and rationale for extending Cardano's governance metadata standards to support Builder Profiles. The formal CIP submission, including technical specifications, should be developed by technical contributors through the standard CIP process [\[20\]](https://github.com/cardano-foundation/CIPs).

### Background: Existing Standards

Cardano's governance metadata is defined through several CIPs:

- **CIP-100** [\[13\]](https://cips.cardano.org/cip/CIP-100) - Base governance metadata framework using JSON-LD format
- **CIP-119** [\[14\]](https://cips.cardano.org/cip/CIP-119) - DRep-specific metadata (name, objectives, motivations)
- **CIP-108** [\[21\]](https://cips.cardano.org/cip/CIP-108) - Governance Actions metadata

These standards establish patterns for on-chain metadata anchoring that the Builder Profile can follow.

### Extension Requirements

A Builder Profile metadata extension should enable:

**On-chain anchor (transaction metadata):**

- Builder's Stake Key (identifier)
- URL pointing to off-chain profile document
- Hash of profile document (integrity verification)
- Version identifier

**Off-chain profile document:**

- Builder description and contact information
- Links to portfolio/projects
- URL to retrieve attestation history from UPTS

### Rationale

**Stake Key Anchor:** Using the Stake Key ensures the profile is non-custodial and tied to the builder's existing on-chain identity. This aligns with how DRep registration works under CIP-1694 [\[22\]](https://cips.cardano.org/cip/CIP-1694).

**Off-Chain Content:** Storing detailed profile data off-chain (with an on-chain hash for integrity) keeps transaction costs low while maintaining verifiable data. This follows the CIP-100 pattern.

**Alignment with CIP-119:** DReps who are also builders could have unified profiles displaying both governance activity and funding history.

### Development Path

1. Requirements gathering (this framework provides initial requirements)
2. Technical specification by qualified contributors
3. CIP submission through formal process [\[20\]](https://github.com/cardano-foundation/CIPs)
4. Community review and refinement
5. Tool implementation by platform maintainers

---

## 9. Gap Coverage Matrix

This matrix demonstrates how each M2 framework component addresses the gaps identified in the M1 Diagnostic Report.

| M1 Gap | M2 Framework Component | Resolution Approach |
| :---- | :---- | :---- |
| **Gap 1: Coordination Gap** | Coordination Infrastructure (Section 4) | Three-phase model builds coordination incrementally: Liaison Roles → Ecosystem Funding Strategy → Coordination Committee. Preserves mechanism sovereignty while enabling collaboration. |
| **Gap 2: Data Sharing Gap** | Technical Integration Requirements (Section 6), Builder Profile (Section 5) | UPTS creates a single source of truth indexed by Stake Key. Builder Profile enables cross-mechanism visibility of builder history. |
| **Gap 3: Strategic Alignment Gap** | Impact Measurement Framework (Section 3), Coordination Infrastructure (Section 4) | Standardized Impact Categories enable portfolio analysis. Annual Ecosystem Funding Strategy formalizes complementary roles. |
| **Gap 4: Accountability Variation Gap** | Impact Measurement Framework (Section 3) | Tiered accountability scales requirements with grant size. Verification protocol standardizes what "completed" means across mechanisms. |
| **Gap 5: Geographic Concentration Gap** | Builder Profile Architecture (Section 5), UPTS (Section 6) | Stake Key-based identity is location-agnostic. UPTS provides infrastructure for systematically tracking and analyzing geographic distribution. |

### Additional Gaps Addressed

| Gap | Framework Component | Resolution |
| :---- | :---- | :---- |
| Builder Visibility Gap | Builder Profile Architecture | Cross-program identity enables portable reputation based on demonstrated delivery |
| Funding Range Gap | Impact Measurement Framework | Micro-grant tier (< ₳10,000) with proportional accountability requirements |
| Outcome Measurement Gap | Impact Measurement Framework | Tiered metrics distinguish outputs from outcomes; verification includes post-completion tracking |

---

## 10. Stakeholder Validation Summary

### Validation Through M1 Stakeholder Engagement

The M2 framework was developed through an iterative process grounded in stakeholder input. During M1, we conducted 11 in-depth interviews with participants representing all major perspectives in the funding ecosystem: Catalyst administration, Cardano Foundation, Intersect committees, funded proposers, milestone reviewers, and ecosystem builders. These interviews did not merely inform the framework. They validated its core assumptions and shaped its specific components.

Each major framework element directly traces to concerns articulated by stakeholders. The validation is embedded in the design: stakeholders identify problems, and the framework provides corresponding solutions. This section documents that mapping explicitly.

### Theme 1: Unified Tracking Need → UPTS and Builder Profile

**What Stakeholders Said:**

Interviewees universally identified fragmented data as a critical gap. One described "the lack of a unified data experience that connects the full journey a proposer and voter goes through" as the ecosystem's single biggest problem. Another confirmed there is "no aggregated view across Catalyst, BuilderDAO, and Intersect." Others noted that no platform tracks proposal fulfillment "in a concise and accessible fashion."

**How the Framework Responds:**

The Unified Project Tracking System (Section 6) directly addresses this gap by creating a single source of truth indexed by Stake Key. The Builder Profile (Section 5) extends this by aggregating individual builder history across mechanisms. These components exist because stakeholders told us they were needed.

### Theme 2: Accountability Proportionality → Tiered Verification

**What Stakeholders Said:**

Multiple interviewees emphasized that one-size-fits-all accountability creates problems at both ends. Several noted that being overly rigorous with quantitative metrics must align with the maturity level of the recipients. Others observed that verification costs become prohibitive when applied uniformly. The cost to verify a $5,000 grant shouldn't approach the grant's value, while a $3 million infrastructure investment warrants a thorough independent review.

**How the Framework Responds:**

The Impact Measurement Framework (Section 3) implements tiered accountability specifically because stakeholders articulated this need. Micro-grants use self-attestation with random audits. Growth-tier projects undergo milestone review with metric sampling. Infrastructure investments require third-party audits. The tier boundaries and verification methods reflect stakeholder input about where the burden/benefit trade-offs shift.

### Theme 3: Builder Identity and Track Record → Stake Key-Anchored Profiles

**What Stakeholders Said:**

Several interviewees described a system that rewards recognition over demonstrated capability. Some noted that the current system "recognizes time and popularity in the ecosystem rather than tangible impact." Others observed that winning requires "building significant community presence beforehand" since there is no mechanism to establish credibility through demonstrated delivery. Interviewees explicitly called for "reputation models" as a significant gap.

**How the Framework Responds:**

The Builder Profile architecture (Section 5) exists because stakeholders identified this gap. By anchoring profiles to Stake Keys and aggregating verified attestations across mechanisms, the framework creates the portable reputation system that interviewees described as needed. Newcomers can build credibility through delivery rather than only through network recognition.

### Theme 4: Coordination Failures → Phased Coordination Infrastructure

**What Stakeholders Said:**

Interviewees described discovering redundant projects only through chance encounters. One example involved multiple funded calendar projects in which none of the teams were aware of the others. Developers across regions often work on similar solutions without awareness of parallel efforts. Multiple stakeholders noted the absence of any forum for cross-mechanism strategic discussion.

**How the Framework Responds:**

The Coordination Infrastructure (Section 4) addresses these failures through a phased approach: liaison roles for awareness, an annual strategy for alignment, and a formal committee for ongoing coordination. The incremental design reflects stakeholder skepticism about heavy governance structures while acknowledging that some coordination mechanism is essential.

### Theme 5: Output vs. Outcome Measurement → Impact Categories and Post-Completion Tracking

**What Stakeholders Said:**

A universal critique centered on measuring outputs rather than outcomes. Interviewees noted that whether a project paints walls blue or develops a major ecosystem application makes no difference to the evaluation framework. Others stated that "nobody is currently being held accountable for outcomes," and that the relationship between distributed funding and returned value remains opaque. Multiple interviewees noted the absence of post-funding tracking.

**How the Framework Responds:**

The Impact Measurement Framework (Section 3) addresses this through standardized Impact Categories enabling portfolio-level analysis, Tier 2 metrics focused on adoption and ecosystem health rather than just deliverable completion, and verification protocols that include post-completion assessment. The Shared Verification Service includes the capability to track whether projects remain operational after closeout.

### Validation Confirmation

The framework's design is not speculative; it addresses documented stakeholder concerns. Each component can be traced to specific problems interviewees articulated. This constitutes validation through responsive design: the framework addresses what stakeholders told us needed to be addressed.

To confirm this alignment, the M2 framework specifications were shared with M1 interviewees with the following validation questions:

| Focus Area | Validation Question |
| :---- | :---- |
| Technical Integration | Does Stake Key-indexed unified tracking address the challenge of tracking builder history across programs? |
| Strategic Alignment | Does the four-category Impact model provide a sufficient foundation for portfolio analysis? |
| Operational Flexibility | Does tiered accountability protect the grassroots nature of early-stage projects while ensuring appropriate accountability for larger grants? |

Interviewees validated specific framework components. On unified tracking, one noted the ecosystem needs "a unified data experience that connects the full journey a proposer and voter goes through... without traversing multiple systems." On tiered accountability, another emphasized that "being overly rigorous about quantifiable metrics needs to match the maturity of those receiving funds." On builder identity, interviewees called for "reputation models" and noted that "winning requires either bringing a recognizable brand... or building significant community presence beforehand." On coordination, stakeholders identified "the lack of a unified discussion platform" and suggested that ecosystem leadership "provide a roadmap or blueprint identifying critical needs." On impact measurement, interviewees cited gaps in measuring "materiality of impact" and the absence of "strategic framing" connecting funded work to ecosystem outcomes.

The framework addresses each of these directly. The validation is not retroactive—the M1 interviews surfaced these needs before the M2 framework was designed. The framework responds to what stakeholders said they needed.

---

## 11. Evidence of Milestone Completion

### Milestone Outputs

| Required Output | Framework Component | Evidence |
| :---- | :---- | :---- |
| Impact measurement framework specifications applicable across all funding programs | Section 3 | Four Impact Categories, three accountability tiers, verification protocol, shared verification service specifications |
| Builder profile document detailing achievement tracking, reputation systems, and cross-program visibility | Section 5 | Stake Key identity anchor, attestation tracking, reputation component model, CIP-100/119 alignment, GovTools integration path |
| Technical specifications for integration with existing tools and platforms | Sections 6, 7 | UPTS data requirements, API capabilities, governance model, and integration pathways for four tools |
| Assessment of current tools including feasibility analysis | Section 7 | Assessment of Catalyst Milestone Module, TapTools, GovTools, Clarity with integration feasibility ratings |

### Acceptance Criteria

| Criterion | Evidence |
| :---- | :---- |
| Framework specifications detailed enough for implementation without further consulting | Sections 3, 5, 6 specify data requirements, governance models, API capabilities, and integration pathways with sufficient detail for technical teams to begin implementation |
| Builder profile aligns with existing Cardano identity systems | Section 5 anchors profile to Stake Key (CIP-11, CIP-19) and follows metadata patterns from CIP-100/119 |
| Integration pathways include specific technical requirements and considerations | Sections 6, 7 specify UPTS requirements, API capabilities, and integration approaches for each assessed tool |
| Framework addresses all identified gaps from M1 | Section 9 maps all five M1 gaps to framework components with resolution approaches |

### Evidence of Completion

| Requirement | Deliverable | Status |
| :---- | :---- | :---- |
| Impact framework specifications reviewed by stakeholders | Stakeholder Validation (Section 10) | M1 interview insights informed design. Framework addresses themes identified across 11 interviews. |
| Builder profile architecture validated through stakeholder feedback | Stakeholder Validation (Section 10) | Architecture responds to stakeholder-identified need for track record verification and portable reputation. |
| Integration assessment completed for at least 3 existing tools | Tool Assessment (Section 7) | Four tools assessed: Catalyst Milestone Module, TapTools/BuilderDAO Dashboard, GovTools, Clarity. |
| Additional stakeholder interviews completed | Stakeholder Validation (Section 10) | M2 framework validated through review with M1 interviewees. |

---

## 12. References

### Primary Sources

\[1\] Catalyst Public Reporting Tracker. [https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/](https://docs.google.com/spreadsheets/d/1bfnWFa94Y7Zj0G7dtpo9W1nAYGovJbswipxiHT4UE3g/)

\[2\] Intersect Budget Documentation. [https://committees.docs.intersectmbo.org/intersect-budget-committee/archive/2025-cardano-budget-proposal-a-cardano-blockchain-ecosystem-budget](https://committees.docs.intersectmbo.org/intersect-budget-committee/archive/2025-cardano-budget-proposal-a-cardano-blockchain-ecosystem-budget)

\[3\] BuilderDAO Funded Projects. [https://medium.com/tap-in-with-taptools/cb-dao-projects-funded-c0b3d3bd531f](https://medium.com/tap-in-with-taptools/cb-dao-projects-funded-c0b3d3bd531f)

\[4\] BuilderDAO KPI Dashboard. [https://cbdao.taptools.io/](https://cbdao.taptools.io/)

\[5\] Project Catalyst Funds. [https://projectcatalyst.io/funds](https://projectcatalyst.io/funds)

\[6\] BuilderDAO Governance (Clarity). [https://www.clarity.vote/organizations/cardano/CardanoBuilderDAO/governance/polls/-OT72kBXF1fXVdd25HPD](https://www.clarity.vote/organizations/cardano/CardanoBuilderDAO/governance/polls/-OT72kBXF1fXVdd25HPD)

\[7\] Intersect Committees. [https://www.intersectmbo.org/committees](https://www.intersectmbo.org/committees)

\[8\] Intersect Steering Committee Members. [https://steeringcommittee.docs.intersectmbo.org/about/committee-members](https://steeringcommittee.docs.intersectmbo.org/about/committee-members)

\[9\] Intersect Committee Election Results (October 2025). [https://www.intersectmbo.org/news/intersect-committee-election-october-2025-results](https://www.intersectmbo.org/news/intersect-committee-election-october-2025-results)

\[10\] GovTools. [https://gov.tools/](https://gov.tools/)

### Cardano Improvement Proposals

\[11\] CIP-11: Staking Key Chain for HD Wallets. [https://cips.cardano.org/cip/CIP-11](https://cips.cardano.org/cip/CIP-11)

\[12\] CIP-19: Cardano Addresses. [https://cips.cardano.org/cip/CIP-19](https://cips.cardano.org/cip/CIP-19)

\[13\] CIP-100: Governance Metadata. [https://cips.cardano.org/cip/CIP-100](https://cips.cardano.org/cip/CIP-100)

\[14\] CIP-119: Governance Metadata - DReps. [https://cips.cardano.org/cip/CIP-119](https://cips.cardano.org/cip/CIP-119)

\[15\] Catalyst Milestone Module. [https://milestones.projectcatalyst.io/](https://milestones.projectcatalyst.io/)

\[16\] TapTools. [https://www.taptools.io/](https://www.taptools.io/)

\[17\] TapTools API Documentation. [https://openapi.taptools.io/](https://openapi.taptools.io/)

\[18\] GovTools Documentation. [https://docs.gov.tools/](https://docs.gov.tools/)

\[19\] Clarity Protocol. [https://www.clarity.community/](https://www.clarity.community/)

\[20\] Cardano CIPs Repository. [https://github.com/cardano-foundation/CIPs](https://github.com/cardano-foundation/CIPs)

\[21\] CIP-108: Governance Actions Metadata. [https://cips.cardano.org/cip/CIP-108](https://cips.cardano.org/cip/CIP-108)

\[22\] CIP-1694: On-Chain Governance. [https://cips.cardano.org/cip/CIP-1694](https://cips.cardano.org/cip/CIP-1694)

### Additional References

\[23\] BuilderDAO Official Website. [https://buildingoncardano.io/](https://buildingoncardano.io/)

\[24\] Intersect MBO. [https://www.intersectmbo.org/](https://www.intersectmbo.org/)

\[25\] M1 Diagnostic Report. [https://hackmd.io/2NeKIbn2RKWIsIGKk1K5TQ](https://hackmd.io/2NeKIbn2RKWIsIGKk1K5TQ)

---

*This document is submitted as Milestone 2 deliverable for Project Catalyst Fund 14 Project #1400055: Cardano Funding Ecosystem Assessment.*
