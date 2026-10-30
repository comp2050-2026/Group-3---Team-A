# ChargeMate Ops
## System Design Document — COMP2050 Assignment 2

**Design team:** Group 3 — Team A  
**Requirements supplied by:** Group 3 — Team B — [FULL WORKSHOP IDENTIFIER AND NICKNAME]  
**Document version:** [VERSION]  
**Document date:** [DATE]  
**Submission deadline:** Sunday 1 November 2026, 23:55 — check the iLearn submission display  
**Document status:** Working template — incomplete and not team-approved

| Team member | Student ID |
|---|---|
| Yousef [CONFIRM OFFICIAL FULL NAME] | [FILL] |
| Harrison McLuckie | [FILL] |
| Cooper Went | [FILL] |
| Isaac Lynn | [FILL] |

---

# Team working guide — remove before final PDF export

This is a ready-to-fill structure, not a completed submission. Replace every `[FILL]`, `[INSERT ...]` and other bracketed instruction. Remove author/reviewer prompts after review. Keep the completed academic content, genuine records, references and final figures.

**A2 project:** Team A is now designing **ChargeMate Ops**, using Team B's SRS. ChargeMate Customer is an external collaborating system.

**Suggested allocation:** Yousef and Harrison lead the technical decisions and final quality checks. Cooper and Isaac own complete, substantive deliverables, with review from the technical leads. These assignments are proposals, not evidence of a past team decision.

| Person | Primary sections | Concrete deliverables | Reviewer |
|---|---|---|---|
| Yousef | 1, 3, 4, 9.1–9.3, 10, 11, 13.1; coordinate 15 | Requirements/interface decisions; architecture and data strategy; trade-offs/concurrency; all 11 RTM rows; SRS reflection; overall document consistency | Harrison |
| Harrison | 6, 7, 8, 12; validate 13.3 and co-review 15 | Three state diagrams and guards; detailed test specifications and plan; check requirement/state/failure coverage; validate sprint analysis against real records | Yousef |
| Cooper | 2, 5 | Original vision; two actor descriptions; complete wireframes and numbered storyboards for UC-01 and UC-03, including failure/recovery screens; revise after review | Yousef checks requirements/UI behaviour; Harrison checks state/test consistency |
| Isaac | 9.4, 13.2–13.3, 14, Appendix; PDF assembly support | Maintenance/deployment strategy; actual A1/A2 tools comparison; collect and caption genuine sprint charts/snapshots; organise interaction records, references and formatting | Yousef reviews maintenance; Harrison reviews evidence and staff-report accuracy |
| Everyone | 13–15 and Appendix | Supply actual contributions, A1/A2 tool experience, sprint records, meeting/discussion evidence and review feedback | Whole team |

## Hand-offs and final checks

- **Yousef → everyone:** Agree the scope, component names, interface responsibilities and provisional assumptions first. Cooper and Isaac can draft in parallel while open decisions are clearly marked.
- **Harrison ↔ Yousef:** Cross-check architecture/data rules against state transitions, tests and the RTM. Resolve conflicting expectations together before final assembly.
- **Cooper → Yousef and Harrison:** Deliver the actual screen figures, actor descriptions and numbered storyboards. Include unknown/unavailable information, denied actions and failed saves. Cooper owns making the revisions identified in review.
- **Isaac → Yousef and Harrison:** Deliver a complete maintenance section and an organised evidence package with dates, captions and source links. Isaac drafts the tools/sprint narrative from actual records; Harrison checks that the interpretation matches those records.
- **Everyone → staff report:** Provide real examples of difficulties, decisions and changes in working method. Yousef writes the coherent SRS reflection from those inputs.
- **Final check:** Yousef checks scope, architecture, RTM and narrative consistency. Harrison checks state logic, test coverage and evidence accuracy. Cooper checks screen readability and storyboard completeness. Isaac checks references, captions, appendix organisation and PDF layout.

The staff report is worth 25 marks and the appendix 10, so the evidence and reflection need substantive review alongside the technical design. Record who actually authored, revised and reviewed each part; do not present the proposed allocation as completed work.

**Working rules**

- Work in the team's existing `a2docs` folder. Suggested main filename: `SDD.md`.
- Use real task/issue/commit/PR links when they exist. Keep review feedback with its actual date.
- Agree component IDs before writing other sections. Reuse the same names in every diagram, RTM row and test.
- Distinguish inherited requirements, provisional assumptions and agreed design decisions.
- A fault must exclude normal availability. Unknown availability is not confirmed zero. Failed saves must not appear successful. Physical movement needs confirmation before its new location is recorded. Fault resolution alone does not establish rental eligibility.
- Record genuine activity. Do not invent historical meetings, attendance, sprint progress, GitHub links, approvals or test results.
- This assessment asks for test **specifications and a plan**. Do not claim tests ran if they did not.
- Final deliverable: one professional PDF, **maximum 50 A4 pages including the appendix**. Aim for 48 pages. Each person also completes the individual contribution evaluation.

## Shared progress board

Fill this with the current position; blank fields are not evidence that work is complete.

| Deliverable | Owner | Current status | Actual draft/task link | Reviewer feedback link | Review date |
|---|---|---|---|---|---|
| Baseline, assumptions, architecture | Yousef | [FILL] | [FILL] | [FILL] | [FILL] |
| Vision and two storyboard/wireframe sets | Cooper | [FILL] | [FILL] | [FILL] | [FILL] |
| Three state diagrams | Harrison | [FILL] | [FILL] | [FILL] | [FILL] |
| Persistence, caching and data access | Yousef | [FILL] | [FILL] | [FILL] | [FILL] |
| Maintenance and deployment | Isaac; Yousef reviews | [FILL] | [FILL] | [FILL] | [FILL] |
| RTM | Yousef | [FILL] | [FILL] | [FILL] | [FILL] |
| Test specifications and plan | Harrison | [FILL] | [FILL] | [FILL] | [FILL] |
| SRS reflection | Yousef; everyone supplies examples | [FILL] | [FILL] | [FILL] | [FILL] |
| Tools comparison and sprint evidence | Isaac drafts/collects; Harrison validates | [FILL] | [FILL] | [FILL] | [FILL] |
| References and interaction appendix | Isaac coordinates; everyone supplies records; Harrison checks evidence | [FILL] | [FILL] | [FILL] | [FILL] |
| Final PDF and consistency review | Yousef + Harrison lead; Cooper + Isaac complete presentation checks | [FILL] | [FILL] | [FILL] | [FILL] |

**Suggested page budget:** cover/contents 2; scope, vision and assumptions 3; remaining system design 13; RTM 4; tests 12; staff report/references 7; appendix 7. Total 48. Adjust to fit the actual material legibly.

---

# Contents

1. Project scope and requirements baseline
2. Project vision
3. Assumptions, clarification gaps and design decisions
4. System architecture and rationale
5. User experience: two wireframe/storyboard sets
6. State diagram 1: FaultRecord
7. State diagram 2: RedistributionJob
8. State diagram 3: OperationalSnapshotQuality
9. Persistent data, caching and maintenance
10. Trade-offs and concurrent processes
11. Requirements Traceability Matrix
12. Test specifications and test plan
13. Report to COMP2050 staff
14. References and resources
15. Final integration and submission checklist
Appendix A. Team interaction log and full records
Appendix B. Evidence index and contributions

**List of figures:** [ADD FINAL FIGURE NUMBERS, TITLES AND PAGE NUMBERS]  
**List of tables:** [ADD IF USEFUL]

---

# 1. Project scope and requirements baseline

**Owner: Yousef | Reviewer: Harrison | Status: [FILL]**

## 1.1 Purpose and intended audience

[FILL: Explain that this SDD plans implementation of ChargeMate Ops for a development team and project managers, and demonstrates the COMP2050 design work.]

## 1.2 System scope and boundary

[FILL: Define staff station monitoring, device tracking, fault management, recorded operational issues and confirmed redistribution. Explain the Harbour North Plaza context.]

| Inside ChargeMate Ops | External responsibility or unresolved boundary |
|---|---|
| [FILL] | [FILL] |
| [FILL] | [FILL] |

[FILL: Identify the primary ChargeMate Operator and the external Rental Station System and Customer-Facing ChargeMate System. Keep customer accounts and payment processing outside Ops. Resolve or explicitly document who owns rental release and return confirmation.]

## 1.3 Received baseline and source documents

| Source ID | Document or recording | Version/date | Exact source location | How it is used |
|---|---|---|---|---|
| SRC-01 | Team B ChargeMate Ops SRS — `SRS (1).pdf` | Cover v1.2, 12 September 2026; verify received baseline | [SHARED FILE LINK] | Primary inherited requirements and fit criteria |
| SRC-02 | Team B handover — `Untitled design (3).mp4` | [VERIFY DATE] | [SHARED FILE LINK] | Explanation; log conflicts with the written SRS |
| SRC-03 | Team A ChargeMate Customer SRS — `Group3_TeamA_COMP2050.pdf` | [VERIFY VERSION/DATE] | [SHARED FILE LINK] | External interface context |
| SRC-04 | Current COMP2050 Assignment 2 instructions | [VERSION/ACCESS DATE] | [ILEARN LINK OR SUPPLIED BRIEF] | Submission requirements |
| SRC-05 | [OTHER SOURCE ACTUALLY USED] | [FILL] | [FILL] | [FILL] |

[FILL: Explain how conflicting document/video statements and later clarifications are handled. Do not silently replace the numbered Ops baseline.]

## 1.4 Requirement reference list

These IDs and titles come from SRC-01 §6, pp.7–9. Read the **full requirement sentences and fit criteria** when designing and testing. The titles alone do not define acceptance.

| ID | Inherited requirement title |
|---|---|
| FR-01 | View Rental Station Status |
| FR-02 | View Power Bank Availability |
| FR-03 | Track Individual Power Bank |
| FR-04 | Record Power Bank Fault |
| FR-05 | Identify Faulty Power Banks |
| FR-06 | Resolve Power Bank Fault |
| FR-07 | Support Power Bank Redistribution |
| FR-08 | Identify Operational Issues |
| NFR-01 | Usability |
| NFR-02 | Operational Data Reliability |
| NFR-03 | Security and Access Control |

Use `Customer.FR-xx` for Team A's earlier requirements when comparing interfaces, because both SRS documents restart their numbering at FR-01.

## 1.5 Use-case baseline

| Source use case | Name | Main SRS location |
|---|---|---|
| UC-01 | View Station Status | SRC-01 pp.12–13; Figure 3 p.16 |
| UC-02 | Track a Power Bank | SRC-01 pp.13–14; Figure 4 p.17 |
| UC-03 | Report and Manage a Faulty Power Bank | SRC-01 pp.14–15; Figure 5 p.18 and note p.19 |
| UC-04 / supporting model | Redistribute Power Banks Between Stations | Historical discussion and overall model; not a fourth fully detailed use case in the final SRS |

[FILL: Explain how FR-07 and FR-08 are covered even though the source has only three detailed use cases. Label new supporting scenarios as design elaborations.]

# 2. Project vision

**Owner: Cooper | Reviewer: Yousef | Status: [FILL]**

[FILL: Write one original paragraph describing the value, intended staff users and operational outcome of your proposed ChargeMate Ops implementation. Do not copy Team B's vision statement.]

# 3. Assumptions, clarification gaps and design decisions

**Owner: Yousef | Reviewer: Harrison | Input: everyone | Status: [FILL]**

## 3.1 Open clarification register

The following are starting questions, not recorded stakeholder answers. Add actual responses and evidence as they arrive.

| Gap ID | Question / ambiguity | Affected requirements | Provisional handling | Actual response/evidence | Status |
|---|---|---|---|---|---|
| GAP-01 | Which fields are exchanged, who owns them, and how current must they be? | FR-01, FR-02, FR-03, NFR-02 | [FILL] | [NOT YET RECORDED] | Open |
| GAP-02 | Who authorises a rental, controls device release and confirms returns? | Cross-system allocation; FR-02, FR-03 | [FILL] | [NOT YET RECORDED] | Open |
| GAP-03 | How are charge eligibility, available counts and return capacity defined? | FR-02, FR-05, FR-07 | [FILL] | [NOT YET RECORDED] | Open |
| GAP-04 | What are the exact device/station states, fault fields and resolution permissions? | FR-01, FR-03–FR-06, NFR-03 | [FILL] | [NOT YET RECORDED] | Open |
| GAP-05 | What are the movement-confirmation, destination-capacity and conflicting-update rules? | FR-07, NFR-02 | [FILL] | [NOT YET RECORDED] | Open |
| GAP-06 | Which recorded issues are displayed, and are any automatic alert rules agreed? | FR-08 | [FILL] | [NOT YET RECORDED] | Open |
| GAP-07 | How are video claims about real-time telemetry, dock blocking and restored availability reconciled with the written SRS? | FR-01, FR-03, FR-05, FR-06, NFR-02 | [FILL] | [NOT YET RECORDED] | Open |
| GAP-08 | [ADD OTHER GAP ACTUALLY IDENTIFIED] | [FILL] | [FILL] | [FILL] | [FILL] |

## 3.2 Design assumptions

| Assumption ID | Explicit assumption | Why it is reasonable | Risk if wrong | Affected design/tests | Validation status |
|---|---|---|---|---|---|
| ASSUMP-01 | [FILL] | [FILL] | [FILL] | [FILL] | [PROVISIONAL / AGREED WITH SOURCE] |
| ASSUMP-02 | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

Do not invent performance targets, charge thresholds, staff roles or alert priorities and present them as inherited requirements.

## 3.3 Design decision log

| Decision ID | Decision and alternatives considered | Rationale | Related requirement/gap | Actual decision date and evidence |
|---|---|---|---|---|
| DEC-01 | [FILL] | [FILL] | [FILL] | [FILL; DO NOT BACKDATE] |
| DEC-02 | [FILL] | [FILL] | [FILL] | [FILL] |

# 4. System architecture and rationale

**Owner: Yousef | Reviewer: Harrison | Status: [FILL]**

## 4.1 Architecture overview

[FILL: Describe the selected architecture, how the operator reaches it, where business rules execute and how external systems connect. Explain your selection.]

**Figure ARCH-01 — ChargeMate Ops architecture:** [INSERT LEGIBLE DIAGRAM]

<!-- Insert the actual diagram here, for example as an image stored under a2docs/diagrams/. Include named components, system boundary, connections and a legend. -->

## 4.2 Component catalogue

These component names are **suggestions from the review**, not SRS-mandated components. Agree or amend them once and update every dependent section.

| Component ID | Suggested name | Final responsibilities | Inputs/outputs | Requirements supported |
|---|---|---|---|---|
| C-UI | Operator Web Interface | [FILL] | [FILL] | [FILL] |
| C-AUTH | Staff Access Control | [FILL] | [FILL] | [FILL] |
| C-MON | Station Monitoring | [FILL] | [FILL] | [FILL] |
| C-DEV | Device Registry | [FILL] | [FILL] | [FILL] |
| C-FAULT | Fault Management | [FILL] | [FILL] | [FILL] |
| C-MOVE | Redistribution Management | [FILL] | [FILL] | [FILL] |
| C-INT | Integration and Reconciliation | [FILL] | [FILL] | [FILL] |
| C-DB | Operational Store | [FILL] | [FILL] | [FILL] |

## 4.3 Requirement-driven architecture rationale

| Requirement or quality concern | Architectural response | Why this response fits | Limitation/trade-off |
|---|---|---|---|
| NFR-01: usability | [FILL] | [FILL] | [FILL] |
| NFR-02: operational data reliability | [FILL] | [FILL] | [FILL] |
| NFR-03: authorised access | [FILL] | [FILL] | [FILL] |
| Consistent fault and movement updates | [FILL] | [FILL] | [FILL] |

## 4.4 External interface responsibilities

| Exchange / operation | Sender → receiver | Required fields | Confirmation/failure handling | Owner/source of truth | Agreement or assumption |
|---|---|---|---|---|---|
| Station/device observations | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| Rental/return information | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| Fault/availability changes | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| Rental release / return confirmation ownership | [FILL] | [FILL] | [FILL] | [FILL] | [UNRESOLVED UNLESS EVIDENCED] |

# 5. User experience: two wireframe/storyboard sets

**Owner: Cooper | Reviewers: Yousef for requirements/UI behaviour; Harrison for state/test consistency | Status: [FILL]**

Use multi-step operator interactions. Suggested choices are UC-01 and UC-03. Include actual screens and the sequence between them, not only a written use-case summary.

## 5.1 Storyboard SB-01 — UC-01 View Station Status

**Actor:** [DESCRIBE AUTHORISED OPERATOR, GOAL, WORKING CONTEXT AND KNOWLEDGE]  
**Preconditions:** [FILL]  
**Requirements:** [FILL]  
**Related tests:** [FILL]

| Step | Screen ID/title | Operator action | System response and information displayed | Next screen / branch |
|---|---|---|---|---|
| 1 | WF-01 — Station overview | [FILL] | [FILL] | [FILL] |
| 2 | WF-02 — Selected station | [FILL] | [FILL] | [FILL] |
| 3 | WF-03 — Attention/recovery view | [FILL] | [FILL] | [FILL] |

**Figures WF-01 to WF-03:** [INSERT ANNOTATED WIREFRAMES]

[FILL: Explain unavailable data, conflicting data, confirmed zero versus unknown availability, attention indicators and recovery navigation.]

## 5.2 Storyboard SB-03 — UC-03 Report and Manage a Faulty Power Bank

**Actor:** [DESCRIBE OPERATOR; DISTINGUISH RESOLUTION PERMISSION IF APPLICABLE]  
**Preconditions:** [FILL]  
**Requirements:** [FILL]  
**Related tests:** [FILL]

| Step | Screen ID/title | Operator action | System response and information displayed | Next screen / branch |
|---|---|---|---|---|
| 1 | WF-04 — Device search/detail | [FILL] | [FILL] | [FILL] |
| 2 | WF-05 — Fault entry | [FILL] | [FILL] | [FILL] |
| 3 | WF-06 — Save result | [FILL] | [FILL] | [FILL] |
| 4 | WF-07 — Later fault review | [FILL] | [FILL] | [FILL] |
| 5 | WF-08 — Resolution entry/result | [FILL] | [FILL] | [FILL] |

**Figures WF-04 to WF-08:** [INSERT ANNOTATED WIREFRAMES]

[FILL: Show not-found, missing information, save failure, unresolved investigation, denied resolution and failed resolution. Later resolution can occur in a different session. Do not show success before a successful save or automatic rental eligibility after resolution.]

# 6. State diagram 1 — FaultRecord

**Owner: Harrison | Reviewer: Yousef | Cooper checks the related screen behaviour | Status: [FILL]**

The object choice is proposed. If replaced, choose another object with meaningful states and update the contents and links.

**Object and purpose:** [FILL]  
**Requirements/use cases:** [FILL]  
**Figure SD-01:** [INSERT UML STATE DIAGRAM]

| Current state | Event | Guard / condition | Action | Next state | Related test |
|---|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Explain valid creation, unresolved investigation, successful resolution, failed save and unauthorised resolution. State what remains unchanged when an operation fails.]

# 7. State diagram 2 — RedistributionJob

**Owner: Harrison | Reviewer: Yousef | Coordinate the movement/data rules with section 9 | Status: [FILL]**

**Object and purpose:** [FILL]  
**Requirements/use cases:** [FILL]  
**Figure SD-02:** [INSERT UML STATE DIAGRAM]

| Current state | Event | Guard / condition | Action | Next state | Related test |
|---|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Distinguish selecting/planning a movement from confirming physical movement and successfully recording completion. Handle faulty/unavailable devices, competing updates and failed recording after a physical move. Mark capacity/in-transit policies as assumptions where not agreed.]

# 8. State diagram 3 — OperationalSnapshotQuality

**Owner: Harrison | Reviewer: Yousef | Cooper checks the related screen behaviour | Status: [FILL]**

**Object and purpose:** [FILL]  
**Requirements/use cases:** [FILL]  
**Figure SD-03:** [INSERT UML STATE DIAGRAM]

| Current state | Event | Guard / condition | Action | Next state | Related test |
|---|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Distinguish reliable available information, unknown, unavailable and inconsistent information. Keep information quality separate from physical device/station health. Do not invent a freshness deadline.]

# 9. Persistent data, caching and maintenance

**Owners: Yousef for 9.1–9.3; Isaac for 9.4 | Reviewers: Harrison for data strategy; Yousef for maintenance | Status: [FILL]**

## 9.1 Persistent data strategy

[FILL: Explain where durable data lives, why this storage is suitable, how identity/relationships are preserved and what transactions must remain consistent.]

| Entity / record | Key fields and relationships | Where stored | Component allowed to read/write | Integrity rule |
|---|---|---|---|---|
| Station | [FILL] | [FILL] | [FILL] | [FILL] |
| PowerBank | [FILL] | [FILL] | [FILL] | [FILL] |
| Fault | [FILL] | [FILL] | [FILL] | [FILL] |
| Redistribution | [FILL] | [FILL] | [FILL] | [FILL] |
| Observation / data quality | [FILL] | [FILL] | [FILL] | [FILL] |
| [OTHER JUSTIFIED RECORD] | [FILL] | [FILL] | [FILL] | [FILL] |

## 9.2 Caching and component data access

[FILL: Say what is cached, where, when invalidated and how stale/last-known facts are labelled. Explain how components request data, access controls and what occurs when a source is unavailable. If you choose no cache, explain why.]

## 9.3 Backup, recovery and retention

[FILL: Describe the proposed approach and how recovery would be checked. Clearly label unconfirmed retention, backup frequency and recovery targets as assumptions.]

## 9.4 Maintenance, updates and deployment

**Owner: Isaac | Reviewer: Yousef | Coordinate with: Harrison on recovery/deployment test coverage**

| System part | Update/deployment approach | Compatibility and failure handling | Rollback/recovery |
|---|---|---|---|
| Operator interface | [FILL] | [FILL] | [FILL] |
| Backend/business logic | [FILL] | [FILL] | [FILL] |
| Database/schema | [FILL] | [FILL] | [FILL] |
| Station/customer adapters | [FILL] | [FILL] | [FILL] |
| External physical devices | [EXPLAIN OWNER/BOUNDARY; DO NOT ASSUME FIRMWARE OWNERSHIP] | [FILL] | [FILL] |

# 10. Trade-offs and concurrent processes

**Owner: Yousef | Reviewer: Harrison | Input: Isaac and Cooper | Status: [FILL]**

## 10.1 Important trade-offs

| Decision | Alternatives | Competing needs | Choice and justification | Limitation |
|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Consider data reliability versus responsiveness, usability versus access controls, deployment complexity and consistency. Explain your actual design choices.]

## 10.2 Concurrent activities and race conditions

| Concurrent events | Possible incorrect outcome | Coordination/guard/priority | Expected failure or conflict response | Related test |
|---|---|---|---|---|
| Fault report versus movement confirmation | [FILL] | [FILL] | [FILL] | [FILL] |
| Two operators update the same device | [FILL] | [FILL] | [FILL] | [FILL] |
| Station/customer events arrive twice or out of order | [FILL] | [FILL] | [FILL] | [FILL] |
| Resolution of one fault while another remains open | [FILL] | [FILL] | [FILL] | [FILL] |
| Local save succeeds while an outgoing update fails | [FILL] | [FILL] | [FILL] | [FILL] |

# 11. Requirements Traceability Matrix

**Owner: Yousef | Reviewer: Harrison | All component owners confirm their allocation | Status: [FILL]**

Keep exactly the five required columns below and one row for every inherited requirement. Use the final architecture names and actual test IDs. Explain meaningful change-impact links; do not fill every cell with every ID.

| Requirement-ID from SRS | Other requirement IDs impacted if it changes | Related use cases | Responsible/affected system components | Related test cases |
|---|---|---|---|---|
| FR-01 | [FILL] | [FILL] | [FILL] | [FILL] |
| FR-02 | [FILL] | [FILL] | [FILL] | [FILL] |
| FR-03 | [FILL] | [FILL] | [FILL] | [FILL] |
| FR-04 | [FILL] | [FILL] | [FILL] | [FILL] |
| FR-05 | [FILL] | [FILL] | [FILL] | [FILL] |
| FR-06 | [FILL] | [FILL] | [FILL] | [FILL] |
| FR-07 | [FILL] | [FILL] | [FILL] | [FILL] |
| FR-08 | [FILL] | [FILL] | [FILL] | [FILL] |
| NFR-01 | [FILL] | [FILL] | [FILL] | [FILL] |
| NFR-02 | [FILL] | [FILL] | [FILL] | [FILL] |
| NFR-03 | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Explain significant dependency links. Put approved new requirements and supporting design safeguards in a separate change/decision register, preserving the received IDs.]

# 12. Test specifications and test plan

**Owner: Harrison | Reviewer: Yousef | Input: all design owners | Status: [FILL]**

Suggested length: approximately 10–15 pages in the final PDF. Specify how the future implementation would be verified. Proposed tests in the earlier review can be reused after checking them against your final design. Keep IDs stable across this section and the RTM.

## 12.1 Test approach and fixtures

[FILL: Explain test levels, requirement/state/branch coverage, simulated external systems, synthetic test data and fault injection. Identify acceptance rules still blocked by unanswered questions.]

| Fixture ID | Synthetic input / setup | Purpose | Relevant assumption |
|---|---|---|---|
| DATA-01 | [FILL: AUTHORISED AND UNAUTHORISED USER FIXTURES] | [FILL] | [FILL] |
| DATA-02 | [FILL: REGISTERED STATIONS/DEVICES] | [FILL] | [FILL] |
| DATA-03 | [FILL: VALID, MISSING AND CONFLICTING OBSERVATIONS] | [FILL] | [FILL] |
| DATA-04 | [FILL: FAULTS, RESOLUTIONS AND MOVEMENT REQUESTS] | [FILL] | [FILL] |

## 12.2 Test inventory

Add a row for every actual test specification. The example IDs below are empty slots, not completed cases or required case counts.

| Test ID | Description | Requirement/decision | Main/success/failure branch | Detailed specification location |
|---|---|---|---|---|
| T-01 | [FILL] | [FILL] | [FILL] | [FILL] |
| T-02 | [FILL] | [FILL] | [FILL] | [FILL] |
| T-03 | [FILL] | [FILL] | [FILL] | [FILL] |

## 12.3 Detailed test-case specifications

### T-01 — [TEST TITLE]

| Field | Specification |
|---|---|
| Requirement(s) / design decision | [FILL] |
| Description and objective | [FILL] |
| Preconditions / initial state | [FILL] |
| Input specification / exact test data | [FILL: IDENTIFIERS, VALUES, PERMISSIONS AND INJECTED FAILURES] |
| Steps | 1. [FILL] <br> 2. [FILL] <br> 3. [FILL] |
| Expected output specification | [FILL: OBSERVABLE UI/API OUTPUT AND PERSISTED STATE] |
| Pass criteria | [FILL: OBJECTIVE EXPECTED RESULT] |
| Cleanup | [FILL] |
| Dependencies / unresolved rules | [FILL OR NONE, WITH EVIDENCE] |

**Duplicate the complete block above for T-02, T-03 and every further test.** Give each case its own input and expected output; do not substitute a title-only list.

### Coverage prompts

- Station data success, unavailable retrieval and conflicting information.
- Confirmed zero availability versus unknown availability.
- Valid device ID, invalid/unknown ID and unknown/conflicting location.
- Valid fault, missing required fields and failed fault save.
- Persistent unresolved-fault exclusion and successful/failed resolution.
- Authorised/unauthorised access, including direct backend requests.
- Confirmed redistribution, unsuitable device, missing confirmation and failed recording.
- Normal operator tasks using visible controls without technical intervention.
- State transitions, concurrent updates and duplicate/late events under the proposed design.
- Customer/station contract behaviour only where responsibilities and rules are established.

## 12.4 Test plan

### Schedule and milestones

This is a proposed **implementation test schedule**, separate from historical A2 design-sprint evidence.

| Milestone | Entry condition | Testing activities / test IDs | Resources and responsible role/person | Proposed timing/dependency | Deliverables / exit condition |
|---|---|---|---|---|---|
| M0 — baseline ready | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| M1 — domain logic ready | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| M2 — integration ready | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| M3 — UI / acceptance ready | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| M4 — release candidate | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

### Environments, resources and reporting

[FILL: Browsers/devices, database, external-system simulators, representative users, test roles, fixtures and tools actually proposed. Describe defect recording, retesting, regression and acceptance reporting.]

### Blocked or conditional test specifications

| Test ID | Missing rule / prerequisite | Gap ID | What can be specified now | What must be confirmed |
|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

Do not include fabricated pass results. If any tests really were run, record build/version, actual data, date, executor, actual result and evidence separately.

# 13. Report to COMP2050 staff

## 13.1 Reflection on using the received SRS

**Owner: Yousef | Reviewer: Harrison | Everyone supplies their actual experience | Status: [FILL]**

Suggested length: approximately 1–3 pages.

[FILL: Which parts were useful? Which ambiguities or contradictions made implementation planning difficult? Give concrete examples. Explain what the team actually did to address them and cite the relevant question, decision or revision. Distinguish a proposed response from a response your team has completed.]

| Concrete issue | Effect on design | Action actually taken | Result / unresolved limitation | Evidence |
|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

## 13.2 Tools, communication and changes from A1 to A2

**Owner: Isaac | Reviewer: Harrison | Everyone supplies their actual experience | Status: [FILL]**

Suggested length: approximately 1–2 pages.

| Activity | What the team actually used in A1 | What the team actually used in A2 | What changed and its effect | Evidence |
|---|---|---|---|---|
| Communication and clarification | [FILL] | [FILL] | [FILL] | [FILL] |
| Tasks and sprint planning | [FILL] | [FILL] | [FILL] | [FILL] |
| Document and diagram authoring | [FILL] | [FILL] | [FILL] | [FILL] |
| Review and version control | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Discuss real benefits/problems with examples. Do not assume the team used a tool simply because this template recommends it.]

## 13.3 Sprint allocations and GitHub burn-up evidence

**Owner: Isaac drafts and organises evidence | Harrison validates charts, interpretation and source links | Everyone supplies genuine records | Status: [FILL]**

Suggested length: approximately 3–4 pages. The brief specifies Sprint 1 from the end of Week 8, Sprint 2 from the end of the mid-session break and Sprint 3 from the end of Week 10, each for two weeks. Fill actual calendar dates from course/team records.

### Sprint 1 — [ACTUAL START AND END DATES]

**Goal:** [ACTUAL GOAL, WITH SOURCE]  
**Allocation snapshot SP1-A:** [INSERT GENUINE SNAPSHOT AND CAPTION]  
**End-of-sprint GitHub burn-up SP1-B:** [INSERT GENUINE CHART AND CAPTION]

| Actual task/issue | Allocated person(s) | Planned work / estimate | Status at sprint end | Evidence |
|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Explain actual scope changes, completed work, carry-over and chart units. Cite the source board/filter and snapshot date.]

### Sprint 2 — [ACTUAL START AND END DATES]

**Goal:** [ACTUAL GOAL, WITH SOURCE]  
**Allocation snapshot SP2-A:** [INSERT GENUINE SNAPSHOT AND CAPTION]  
**End-of-sprint GitHub burn-up SP2-B:** [INSERT GENUINE CHART AND CAPTION]

| Actual task/issue | Allocated person(s) | Planned work / estimate | Status at sprint end | Evidence |
|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Explain actual progress, scope changes and carry-over.]

### Sprint 3 — [ACTUAL START AND END DATES]

**Goal:** [ACTUAL GOAL, WITH SOURCE]  
**Allocation snapshot SP3-A:** [INSERT GENUINE SNAPSHOT AND CAPTION]  
**End-of-sprint GitHub burn-up SP3-B:** [INSERT GENUINE CHART AND CAPTION]

| Actual task/issue | Allocated person(s) | Planned work / estimate | Status at sprint end | Evidence |
|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Explain actual progress, remaining work and final review.]

### Evidence limitations

[FILL: Disclose any missing snapshots/records. If reconstructing a chart from genuine timestamped history, label the method and limits; do not call it an original snapshot. A1 minutes are not A2 sprint evidence.]

# 14. References and resources

**Owner: Isaac coordinates | Reviewer: Harrison | Everyone adds sources they actually used | Status: [FILL]**

| Reference ID | Author / organisation | Resource title | Version/date and access date | Link / source location | Where used |
|---|---|---|---|---|---|
| REF-01 | Team B | ChargeMate Ops SRS | [FILL] | [FILL] | [FILL] |
| REF-02 | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

[FILL: Include diagram tools, borrowed assets/templates, technical resources and AI assistance actually used, with the required acknowledgement. Cite sources within the relevant sections as well as in this list.]

# 15. Final integration and submission checklist

**Coordinators: Yousef and Harrison | Cooper checks wireframes/storyboards; Isaac checks references, evidence captions and PDF layout**

Move this checklist to the team's working records or remove it from the final PDF if it is not useful to the submission audience.

- [ ] All names, IDs, full workshop/team identifiers and paired-team nickname are correct.
- [ ] The design target is ChargeMate Ops; Customer responsibilities are clearly separated.
- [ ] Vision is original; source baseline and assumptions are clear.
- [ ] Architecture figure names components and their connections; rationale covers FRs and NFRs.
- [ ] Two multi-step use cases have actor descriptions, actual wireframes and numbered storyboards.
- [ ] Three object state diagrams include meaningful states, events and guards.
- [ ] Persistence, caching, component access, maintenance and deployment are explained.
- [ ] Trade-offs and concurrent processes/race conditions are addressed.
- [ ] RTM has all 11 inherited requirement rows and the five required columns.
- [ ] Every RTM component and test ID exists and uses the same name throughout.
- [ ] Test cases contain IDs, descriptions, inputs and expected outputs; plan includes resources, schedule, milestones and deliverables.
- [ ] Staff report reflects actual work and includes A1/A2 tools and genuine sprint evidence.
- [ ] Appendix contains all required genuine meeting/discussion records.
- [ ] Sources/resources and actual assistance are acknowledged.
- [ ] All placeholders, drafting prompts and working-guide material are removed or completed.
- [ ] Latest exported PDF is legible, consistently numbered and no more than 50 A4 pages including appendices.
- [ ] Group PDF is submitted through iLearn and receipt checked.
- [ ] Each member completes the individual contribution evaluation within the stated five-day grace period.

# Appendix A. Team interaction log and full records

**Coordinator: Isaac | Reviewer: Harrison | Everyone supplies their own genuine records**

Include meetings and discussions held in person, through chat and online. Add rows only for actual interactions; attach or transcribe the full relevant records with their source context.

## A.1 Interaction index

| Record ID | Actual date/time | Channel/place | Evidenced participants | Topic | Full record location |
|---|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

## A.2 Full record template — duplicate for each actual interaction

**Record ID:** [FILL]  
**Actual date/time:** [FILL]  
**Channel/place:** [FILL]  
**Participants/attendance:** [FILL FROM EVIDENCE]  
**Recorder/source:** [FILL]  
**Agenda/topic:** [FILL]

**Discussion:** [RECORD WHAT WAS ACTUALLY DISCUSSED]

**Decisions:** [RECORD ACTUAL DECISIONS, OR STATE NONE]

| Action | Actual owner | Due date if agreed | Status at the time of the record |
|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] |

**Unresolved points:** [FILL]  
**Source link / evidence reference:** [FILL]

# Appendix B. Evidence index and contributions

## B.1 Evidence index

| Evidence ID | What it demonstrates | Actual date/period | Source link/file | Related section |
|---|---|---|---|---|
| [FILL] | [FILL] | [FILL] | [FILL] | [FILL] |

## B.2 Individual contributions supported by evidence

These are actual contributions, not the proposed allocation in the working guide.

| Team member | Work actually contributed | Review/collaboration actually performed | Supporting issue/commit/PR/record |
|---|---|---|---|
| Yousef | [FILL] | [FILL] | [FILL] |
| Harrison | [FILL] | [FILL] | [FILL] |
| Cooper | [FILL] | [FILL] | [FILL] |
| Isaac | [FILL] | [FILL] | [FILL] |
