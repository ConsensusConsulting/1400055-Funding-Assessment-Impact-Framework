# **Cardano Funding Ecosystem - M3 Implementation Planning & Recommendations**

**Report Date:** February 2026  
**Version:** 2.1  
**Prepared By:** Consensus Consulting LLC  
**Report Type:** Implementation Planning (Milestone 3\)  
**Project:** Fund 14 Ecosystem Assessment (Project 1400055\)

## **Executive Summary**

This document delivers Milestone 3 for the Cardano Funding Ecosystem Assessment project. Building on the diagnostic findings from M1 and the framework specifications from M2, this document translates research into action through prioritized recommendations, design approaches for key framework components, an implementation roadmap, and a coordination blueprint.

The recommendations are organized into two categories: items that can begin immediately and those that require formal approval. The design approaches for Liaison Roles and Builder Profiles provide direction for stakeholder consultation and requirements gathering without prescribing technical implementation. The implementation roadmap sequences activities based on dependencies, progressing from validation through stakeholder identification, requirements gathering, design, and implementation.

This document completes the planning phase. Implementation requires dedicated resources and teams beyond the scope of this assessment. The deliverable provides a foundation for future implementation work.

The full M1 Diagnostic Report is available at: [https://hackmd.io/@ConsensusConsulting/rJhIiX3QWl](https://hackmd.io/@ConsensusConsulting/rJhIiX3QWl)

The full M2 Framework Specifications are available at: [https://hackmd.io/@ConsensusConsulting/SkbIuFNHbg](https://hackmd.io/@ConsensusConsulting/SkbIuFNHbg)

## **Table of Contents**

1\. Final Recommendations Report  
2\. Liaison Roles: Design Approach  
3\. Builder Profile: Design Recommendations  
4\. Implementation Roadmap  
5\. Coordination Blueprint  
6\. Evidence of Milestone Completion  
7\. References

## **1\. Final Recommendations Report**

### **Introduction**

The following recommendations are based on M1 stakeholder interviews and M2 framework development. Each addresses documented gaps and has been validated through stakeholder engagement. The recommendations are organized into three priority tiers based on governance requirements, enabling immediate progress on items requiring no formal approval while building toward actions that require ecosystem-wide coordination.

### **Priority 1: Immediate Actions**

These actions can begin without formal approval from any funding mechanism. They require willingness and cooperation rather than governance processes.

**1.1 Cross-Mechanism Liaison Communication**  
Each funding mechanism should designate an informal liaison to monitor the governance processes of other mechanisms and share information. Stakeholder interviews identified coordination failures as a universal concern. One interviewee described discovering multiple funded calendar projects, with none of the teams aware of the others. The liaison model addresses this through awareness rather than authority.

For Catalyst, this means identifying a team member to attend BuilderDAO governance calls and Intersect committee meetings. For BuilderDAO, a member would attend Catalyst town halls and Intersect sessions. For Intersect, committee representation would observe Catalyst and BuilderDAO processes.

This requires no governance approval. It can begin within 30 days, provided participants are willing.

**1.2 Cross-Mechanism Project Registry**  
A shared document listing all active funded projects across mechanisms would provide immediate visibility without infrastructure investment. Stakeholders consistently identified fragmented data as the ecosystem's biggest gap. One described needing "a unified data experience that connects the full journey a proposer and voter goes through."

The initial version can be a simple spreadsheet that compiles existing project lists from the Catalyst Milestone Module, the BuilderDAO dashboard, and the Intersect committee documentation. It should include the project name, mechanism, funding amount, status, and primary contact. Monthly updates would maintain currency.

An initial version could be published within 60 days, given access to existing project data from each mechanism.

**1.3 Coordination Touchpoint Documentation**  
Some coordination already occurs through personal relationships and informal channels. Documenting these touchpoints makes them visible and sustainable beyond individual relationships.

This involves interviewing liaison contacts at each mechanism, identifying existing information-sharing practices, and publishing documentation of the current coordination state. The output serves as a baseline for measuring improvements in coordination.

This can be completed within 90 days with cooperation from the mechanism representatives.

### **Priority 2: Near-Term Actions**

These actions require approval from individual funding mechanisms but not ecosystem-wide governance.

**2.1 Formalize Liaison Roles**  
Once informal liaison communication proves valuable, each mechanism should formally designate a liaison with defined responsibilities and compensation. Volunteer coordination is unsustainable over time. Formalizing roles ensures continuity and accountability.

Each mechanism would approve the liaison role through its governance process, define responsibilities, including attendance requirements and reporting cadence, and establish compensation from its budget.

Catalyst would include this in its operational budget. BuilderDAO would require a member vote. Intersect would need committee approval. Timeline is 3 to 6 months from initiation, depending on governance cycles.

**2.2 Tiered Accountability Pilot**  
The M2 framework specifies three accountability tiers based on grant size: Micro-grant, Growth, and Infrastructure. Stakeholders emphasized that "being overly rigorous about quantifiable metrics needs to match the maturity of those receiving funds." The tiered model addresses this, but needs validation before ecosystem-wide adoption.

A pilot would select one Catalyst fund cycle to test differentiated verification requirements based on grant size, document outcomes and lessons learned, and publish results for community review.

This requires Catalyst operational approval and milestone reviewer training on differentiated requirements.

### **Priority 3: Strategic Actions**

These actions require formal governance processes, which may include DRep approval.

**3.1 Unified Project Tracking System**  
The UPTS specified in M2 would create shared infrastructure aggregating project data from all treasury-funded mechanisms. This addresses the Data Sharing Gap identified in M1. Mandatory participation requires governance authority beyond any single mechanism.

Implementation requires securing budget allocation through the Intersect annual budget process, developing technical specifications and an RFP for implementation, submitting a governance action requiring mechanism participation, and procuring a development team.

**3.2 Ecosystem Funding Coordination Committee**  
The M2 framework specifies a formal coordination committee as the third phase of coordination infrastructure, after liaison roles and the annual strategy process prove value. The committee would have advisory authority over ecosystem coordination but no directive authority over individual mechanism decisions.

Implementation requires successful completion of earlier coordination phases, drafting a committee charter outlining its composition and mandate, submitting a governance action to establish the committee, and conducting inaugural elections.

**3.3 Builder Profile CIP**  
The Builder Profile architecture should align with existing CIP-100 and CIP-119 patterns. Formal CIP submission ensures community review and standard adoption across ecosystem tools.

This requires a technical contributor to draft the specification per the CIP template, submit it through the formal CIP process, incorporate community feedback, and support tool implementers in adoption.

### **Recommendation Summary**

| Recommendation | Priority | Governance Required | Timeline |
| :---- | :---- | :---- | :---- |
| Cross-mechanism liaison communication | 1 | None | 30 days |
| Cross-mechanism project registry | 1 | None | 60 days |
| Coordination touchpoint documentation | 1 | None | 90 days |
| Formalize liaison roles | 2 | Mechanism-level | 3-6 months |
| Tiered accountability pilot | 2 | Mechanism-level | 6 months |
| Unified Project Tracking System | 3 | DRep governance | See roadmap |
| Coordination Committee | 3 | DRep governance | See roadmap |
| Builder Profile CIP | 3 | CIP process | See roadmap |

## **2\. Liaison Roles: Design Approach**

### **Purpose and Objectives**

This section describes the approach for validating and refining the Liaison Roles component of the Coordination Infrastructure. Rather than a formal pilot requiring dedicated resources, validation is conducted by the Ecosystem Funding Working Group itself. The working group participants already represent the cross-mechanism perspectives that liaison roles would formalize.

The objectives are to validate whether cross-mechanism observation improves coordination, identify practical barriers to information sharing, document coordination opportunities that emerge from working group discussions, and gather input to inform whether and how to formalize roles.

### **Stakeholder Consultation**

The 11 stakeholders interviewed during M1 represent the initial pool for ongoing consultation and feedback. These participants span Catalyst administration, Cardano Foundation, Intersect committees, funded proposers, and ecosystem builders. They have already demonstrated engagement through M1 interviews and represent the stakeholder diversity needed to validate the liaison model.

| Stakeholder Perspective | Count | Value to Consultation |
| :---- | :---- | :---- |
| Catalyst Administration | 2 | Direct insight into Catalyst operations and constraints |
| Cardano Foundation | 2 | Cross-ecosystem perspective, milestone review experience |
| Intersect Committees | 2 | Governance and budget process knowledge |
| Funded Proposers | 3 | Builder perspective on coordination gaps |
| Ecosystem Builders | 2 | Independent perspective on mechanism effectiveness |

Additional stakeholders will be identified through the working group process. The goal is to understand who currently performs informal liaison functions, what information they share, what gaps exist, and what would make formalizing these functions valuable.

### **Validation Approach**

Validation happens through the working group's regular meeting cadence rather than a separate pilot program. Working group discussions surface coordination gaps in real time. Participants who already observe multiple mechanisms share their insights. The group documents instances where cross-mechanism awareness would have prevented duplication or enabled collaboration.

This approach acknowledges that participants are not compensated for pilot activities. The working group meetings that they already attend provide a venue to test whether liaison functions add value. If working group members find that cross-mechanism updates are useful, that provides evidence for formalization. If the updates feel redundant or unhelpful, that informs a different approach.

### **Success Indicators**

Success is measured qualitatively through working-group feedback rather than by quantitative targets. The key questions are whether working group participants find cross-mechanism updates valuable; whether coordination opportunities arise from shared awareness; whether participants can identify specific instances where liaison visibility would have helped; and whether there is support for formalizing roles with dedicated resources.

These questions are answered through working group discussion and documented in meeting notes. The outcome is a recommendation on whether to proceed with formalization, what the liaison role should entail, and the resources required.

### **Deliverables**

If the working group proceeds with this approach, the validation process would produce documentation of current informal coordination practices, a working group assessment of liaison value, and a recommendation on whether to formalize roles with defined resource requirements.

## **3\. Builder Profile: Design Recommendations**

### **Purpose and Scope**

This section provides design recommendations for the Builder Profile architecture described in M2. The recommendations guide stakeholder consultation and requirements gathering without prescribing technical implementation details. Technical specifications are the responsibility of implementation teams working with qualified developers.

The Builder Profile concept addresses the Reputation Gap identified in M1. Builders lack a portable way to demonstrate their track record across funding mechanisms. The profile would link verified achievements to a persistent identity, enabling funders and voters to assess builder credibility.

### **Design Principles**

The M2 framework established core principles that should guide requirements gathering and design. The identity anchor should be the Cardano Stake Key, providing a persistent identifier that builders control without relying on centralized identity providers. The profile should follow existing CIP patterns, specifically CIP-100 for governance metadata, ensuring compatibility with ecosystem tools. Attestations should record verified achievements from funding mechanisms, creating a track record that builders can reference across contexts.

These principles inform consultation with stakeholders. Technical decisions on data structures, storage mechanisms, and API design should be informed by requirements gathering with qualified technical contributors.

### **Stakeholder Requirements**

Before any technical work begins, requirements must be gathered from the stakeholders who would use or provide data to the Builder Profile system.

Builders need to understand what information they want to display, how they want to control their profile, and what would make the profile useful when applying for funding or demonstrating credibility.

Funding mechanisms need to understand what attestations they could provide, what systems changes would be required, and what governance approvals would be needed to participate.

Ecosystem tools need to understand which queries they will run against profile data, how they will integrate profiles into existing interfaces, and the technical constraints they face.

The working group facilitates these consultations. Requirements are documented and validated with stakeholders before any design work proceeds.

### **Integration Considerations**

The Builder Profile would need to integrate with existing ecosystem infrastructure. GovTools is a potential integration point for displaying builder profiles alongside DRep information. The Catalyst Milestone Module is a potential source of attestation for project completion records. These integrations require buy-in from the teams that maintain these systems.

Integration requirements should be gathered through direct consultation with tool maintainers. The assessment does not prescribe specific technical approaches. Those decisions belong to the teams that would implement and maintain the integrations.

### **Success Indicators**

Success at this stage is measured by progress on requirements and design, not by system deployment. The key indicators are whether stakeholder requirements are documented and validated, whether technical contributors are identified and engaged, whether integration feasibility is assessed with relevant tool teams, and whether a design specification is produced that implementation teams can build from.

These indicators align with the phased roadmap. Requirements and design work happen before implementation budgets are requested.

### **Deliverables**

If the working group proceeds with requirements gathering, the process would produce stakeholder requirements documentation capturing builder, mechanism, and tool needs; identification of technical contributors to connect the effort with qualified developers; an integration feasibility assessment based on consultation with tool maintainers; and a design recommendation informing whether to proceed with implementation and what resources would be needed.

## **4\. Implementation Roadmap**

### **Phased Approach**

The implementation roadmap organizes recommendations into phases. Phase 1 is grounded in the Ecosystem Funding Working Group's Q1 cadence. Subsequent phases progress from stakeholder identification through requirements gathering, design, and implementation, with the goal of completing design work in 2026\.

### **Phase 1: Validation & Alignment (Q1 2026\)**

Phase 1 establishes the framework based on working group consensus. The diagnostic findings and proposed components require validation by practitioners before proceeding. This phase ensures the recommendations reflect real ecosystem needs and builds the coalition necessary to carry work into subsequent phases.

| Date | Working Group Focus | Outcome |
| :---- | :---- | :---- |
| Feb 11 | Review M3, validate recommendations | Alignment on priority components |
| Feb 25 | Liaison Roles design, identify participants | Validation approach confirmed |
| Mar 11 | Builder Profile requirements discussion, identify technical contributors | Requirements gathering underway |
| Mar 25 | Cross-committee consultation | Broader stakeholder input |

### **Phase 2: Stakeholder Identification & Requirements (Q2 2026\)**

Phase 2 maps stakeholders and begins gathering requirements in parallel. For components where stakeholders are already known, requirements work can begin immediately. For others, stakeholder identification precedes requirements gathering.

* Identify the consumers for each framework component. A unified tracking system serves different users than a builder reputation system. Coordination infrastructure affects mechanism leadership differently than individual builders. Understanding who uses what determines whose input matters for each component.  
* Map the technical stakeholders who understand existing systems. Catalyst has the Milestone Module. BuilderDAO has TapTools integration. Intersect has committee documentation. The people who built and maintain these systems know constraints and integration options.  
* Begin gathering functional requirements from identified stakeholders. What does a builder profile need to contain? What queries does a unified tracking system need to support? What information do liaison roles need to share?  
* Build relationships with the mechanism leadership. Coordination infrastructure requires participation from Catalyst, BuilderDAO, and Intersect. Relationships built in this phase enable the collaboration required for design and implementation.

### **Phase 3: Requirements Validation & Scoping (Q3 2026\)**

Phase 3 completes requirements gathering and validates findings with stakeholders. This is where specifications meet operational reality, and scope is confirmed.

* Validate requirements with stakeholders before moving to design. Requirements gathered without validation produce systems nobody uses. Confirmation ensures alignment between what is proposed and what is needed.  
* Define what needs to be built versus what already exists. Some components may require new infrastructure. Others may involve integrating or extending existing tools. This phase distinguishes between the two.  
* Understand the technical landscape and constraints. What data is already captured by existing systems? What APIs exist or could be extended? What governance processes would need to change? Technical stakeholders surface the realities that shape feasibility.  
* Finalize scope for design work. Not everything identified in M2 needs to be built at once. This phase determines what to prioritize for the initial design and implementation effort.

### **Phase 4: Design (Q4 2026\)**

Phase 4 produces technical designs and specifications based on validated requirements. This is where requirements become architectures, data models, and interface specifications.

* Translate validated requirements into technical architecture. Define how components interact, where data lives, and what the integration points with existing systems.  
* Produce specifications detailed enough for implementation teams to build from. Database schemas, API contracts, user flows, governance processes. Design work ends when a qualified team can begin building without ambiguity.  
* Conduct stakeholder review of proposed designs. The people who provided requirements review the designs to confirm that their needs are addressed.  Misalignments surface before implementation begins.


Completing the design in Q4 2026 positions the ecosystem to request implementation funding in the 2027 budget cycle, with clear specifications and validated requirements.

### **Phase 5: Implementation (2027)**

Phase 5 builds the designed components. This is where specifications become working systems.

* Build approved components in accordance with design specifications. Implementation may be phased, starting with the highest-priority components or those with the fewest dependencies.  
* Pilot with limited scope before broad deployment. Initial users surface issues that the design work missed. Iteration based on pilot feedback improves the system before ecosystem-wide rollout.  
* Integrate with existing ecosystem tools. A unified tracking system has limited value if it does not integrate with the systems where builders and voters already work. Implementation includes the integration work necessary for adoption.

### **Phase 6: Operations (Ongoing)**

Phase 6 maintains and evolves deployed systems. Building is not the end. Sustaining is an ongoing responsibility.

* Maintain deployed systems to ensure reliability and availability. Infrastructure requires ongoing attention. Someone needs to be responsible for keeping things running.  
* Manage coordination functions on an ongoing basis. Liaison roles require people. Annual strategy processes require facilitation. Coordination infrastructure is not a one-time build. It is an ongoing function.  
* Iterate based on ecosystem feedback. Requirements evolve as the ecosystem changes. Systems built today will need updates tomorrow. Operations include continuous improvement.

### **Dependencies**

| Phase | Depends On |
| :---- | :---- |
| Stakeholder Identification & Requirements | Working group alignment on priority components |
| Requirements Validation & Scoping | Stakeholders identified and engaged |
| Design | Requirements validated with stakeholders |
| Implementation | Design approved, resources secured |
| Operations | Successful implementation |

## **5\. Coordination Blueprint**

### **Working Group Structure**

Effective coordination requires perspectives beyond the mechanisms themselves. The coordination structure should include independent advisors with grants and ecosystem experience who can provide objective guidance without allegiance to any single entity.

Intersect has established an Ecosystem Funding Working Group examining coordination across funding mechanisms. This assessment's recommendations align with and can inform the working group's efforts. The relationship positions this assessment to provide a research foundation, specify framework components, design pilot programs, and document stakeholder needs. The working group provides governance authority, determines adoption priorities, oversees pilot execution, and represents stakeholder interests. Assessment outputs serve as input to the working group's deliberations. Implementation decisions rest with the working group and broader Intersect governance.

### **Working Group Functions**

Based on M1 and M2 findings, an effective coordination working group addresses four areas.

Information sharing involves maintaining cross-mechanism project visibility, publishing coordination briefings, and identifying duplication and overlap.

Strategic alignment involves facilitating the annual development of the Ecosystem Funding Strategy, documenting the complementary roles of each mechanism, and tracking the funding portfolio against ecosystem priorities.

Standards development involves coordinating technical standards for the Builder Profile and UPTS requirements, ensuring interoperability across mechanism systems, and guiding CIP development to meet funding ecosystem needs.

Pilot oversight includes validating the liaison role, monitoring the Builder Profile requirements process, and evaluating results to recommend next steps.

### **Decision Framework**

The coordination structure has advisory authority rather than directive power over funding mechanisms. This limitation preserves mechanism sovereignty while enabling coordination.

The coordination structure can publish recommendations, facilitate information sharing, coordinate pilot programs, develop standards proposals, and produce analysis and reports. It cannot approve or reject funding proposals, mandate changes to mechanism policy, reallocate funds between mechanisms, or override mechanism governance.

The decision process for coordination recommendations follows five steps. The working group drafts a recommendation based on research and stakeholder input. Mechanisms review and provide feedback. The working group revises based on feedback. Mechanisms decide whether to adopt within their governance processes. The working group documents outcomes and lessons learned.

### **Sustainability Model**

The sustainability model evolves across phases, matching the implementation roadmap.

During Phase 1, coordination functions are conducted through volunteer participation, working-group meetings using existing Intersect infrastructure, and documentation via shared resources.

As phases progress, coordination functions formalize through defined liaison roles across mechanisms, dedicated coordination support, and infrastructure investment as components are built.

In later phases, if the Coordination Committee is established, operations include committee functions per M2 specification and ongoing infrastructure maintenance.

### **Governance Integration**

The coordination structure integrates with existing governance rather than creating parallel authority. The Intersect Steering Committee receives coordination reports and provides strategic direction. The Intersect Budget Committee reviews coordination budget requests. Catalyst Administration designates the Catalyst liaison and receives coordination input. BuilderDAO Governance designates the BuilderDAO liaison and considers coordination recommendations. The DRep Community approves governance actions to establish formal committees.

## **6\. Evidence of Milestone Completion**

### **Milestone Outputs**

| Required Output | Section | Evidence |
| :---- | :---- | :---- |
| Final Recommendations Report with Prioritized Actions | Section 1 | Three priority tiers with 8 recommendations |
| Pilot program design with selection criteria and metrics | Sections 2-3 | Design approaches with stakeholder criteria and success indicators |
| Implementation roadmap with phased approach | Section 4 | Six-phase roadmap with 2026 design completion target |
| Coordination blueprint with sustainability model | Section 5 | Working group functions, decision framework, governance integration |

### **Evidence of Completion**

| Requirement | Deliverable | Status |
| :---- | :---- | :---- |
| Final recommendations report published | This document, Section 1 | Complete |
| Pilot design with 10+ participants | Sections 2-3 with M1 interviewee pool | Complete |
| Implementation roadmap shared | Document for working group review | Complete |
| Coordination blueprint validated | Aligned with Ecosystem Funding Working Group | Complete |

## **7\. References**

### **Project Documents**

\[1\] M1 Diagnostic Report. https://hackmd.io/@ConsensusConsulting/rJhIiX3QWl  
\[2\] M2 Framework Specifications. https://hackmd.io/@ConsensusConsulting/SkbIuFNHbg

### **Cardano Ecosystem Resources**

\[3\] Intersect Budget Documentation. https://committees.docs.intersectmbo.org/intersect-budget-committee/archive/2025-cardano-budget-proposal-a-cardano-blockchain-ecosystem-budget  
\[4\] Catalyst Milestone Module. https://milestones.projectcatalyst.io/  
\[5\] BuilderDAO KPI Dashboard. https://cbdao.taptools.io/  
\[6\] GovTools. https://gov.tools/  
\[7\] Intersect Committees. https://www.intersectmbo.org/committees

### **Cardano Improvement Proposals**

\[8\] CIP-11: Staking Key Chain for HD Wallets. https://cips.cardano.org/cip/CIP-11  
\[9\] CIP-19: Cardano Addresses. https://cips.cardano.org/cip/CIP-19  
\[10\] CIP-100: Governance Metadata. https://cips.cardano.org/cip/CIP-100  
\[11\] CIP-119: Governance Metadata \- DReps. https://cips.cardano.org/cip/CIP-119

*This document is submitted as Milestone 3 deliverable for Project Catalyst Fund 14 Project \#1400055: Cardano Funding Ecosystem Assessment.*
