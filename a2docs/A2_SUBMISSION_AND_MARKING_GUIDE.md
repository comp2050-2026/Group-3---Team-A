---
title: COMP2050 A2 Design Proposal Submission and Marking Guide
tags:
  - comp2050
  - assessment/a2
  - design-proposal
  - marking
updated: 2026-07-22
status: verify-a2-release
---

# A2 Design Proposal — Submission and Marking Guide

> [!warning] 2026 date and historical project-name check
> The supplied historical A2 brief names Project A as `NPW-squirrel-network`, Project B as `NPW-squarker`, and gives “Sunday 2 November” as the due date. Those names and that calendar marker are not the released 2026 scenario. For 2026, the official Unit Guide gives **Sunday, 1 November 2026**, while the released A1 projects are **Project A: ChargeMate Customer** and **Project B: ChargeMate Ops**. Confirm the later A2 specification and rubric in iLearn when released.

## Background and project swap

A2 moves from analysis to design. A team does not design the same project it analysed in A1. Instead, in the Week 8 practical it receives the A1 handover package for the project where it previously acted as client.

The handover should include:

- SRS.
- Use-case diagram.
- Three use-case descriptions.
- Three interaction diagrams.
- Handover explainer video.

The receiving team uses these artefacts to design a system that meets the supplied requirements. It should review the handover carefully during Week 8 and contact the Unit Convenor if serious problems prevent a reasonable design response.

## Audience and assessment philosophy

Like A1, A2 does not rely on a traditional prescriptive rubric. It rewards professional judgement, creativity, clear explanation and careful thinking about a non-trivial problem.

The System Design Document has two audiences:

- The teaching team, which evaluates the unit learning outcomes.
- A fictitious development team and its project managers, who should be able to plan implementation from the document.

## Project management and sprints

Teams maintain A2 artefacts and project records in GitHub and work in three two-week sprints:

1. Sprint 1 begins at the end of Week 8.
2. Sprint 2 begins at the end of the mid-session break.
3. Sprint 3 begins at the end of Week 10.
4. A2 is due at the end of Week 12.

The submission includes snapshots showing sprint allocations and the GitHub burn-up chart at the end of each sprint.

## Group submission

Submit one professional PDF, no more than 50 A4 pages, containing the following.

### Identification

- Team name.
- Team members' names and student IDs.
- The source requirements team's formal workshop/group/team name and nickname.

### System Design Document

- A new vision statement for the design project, not a direct copy from the partner SRS.
- System-architecture diagram showing the overall system, subsystem/component names and connections.
- Explanation of the architecture choice and how functional and non-functional requirements influenced it.
- Sample wireframes/screen designs and a storyboard for two multi-step use cases.
- Description of the actor performing each selected interaction.
- Design assumptions arising from gaps or ambiguity in the received SRS.
- Three state diagrams for objects with interesting states or complex behaviour.
- Storage and persistent-data strategy, including storage, caching and component data access.
- Maintenance/update/deployment strategy for websites, mobile apps, desktop clients, external devices or other relevant components.
- Important trade-offs and choices, including tensions between quality attributes such as features, performance and security.
- Concurrent processes and how race conditions, coordination, guarding or priorities are handled.
- A reviewed list of assumptions. Assumptions must explain decisions, not excuse weak design.

### Requirements Traceability Matrix

One row per requirement, with these columns:

| Column | Purpose |
| --- | --- |
| Requirement ID | Identifier from the received SRS. |
| Impacted requirement IDs | Other requirements that may be affected by a change. |
| Related use cases | Use cases that realise or depend on the requirement. |
| System components | Architecture components responsible for or affected by the requirement. |
| Related test cases | Test cases that verify the requirement. |

### Test specifications

Include test-case specifications with:

- Test-case identifier.
- Test description.
- Input specification/test data.
- Expected output specification.

Also include a test plan covering schedule, resources, milestones, processes and test deliverables. The supplied brief suggests approximately 10–15 pages for this section.

### Report to COMP2050 staff

- Reflection on how easy or difficult the received SRS was to use, challenges encountered and how the team responded (approximately 1–3 pages).
- Overview of tools and communication methods used in A1 and how the team's working method changed for A2 (approximately 1–2 pages).
- Sprint-tracking snapshots and GitHub burn-up progress at the end of each sprint (approximately 3–4 pages).
- References and resources used.

### Appendix

- Log of team interactions, including minutes from in-person, chat and online meetings/discussions.

## Individual team evaluation

After the group assignment is submitted, every student completes the individual-contribution team-evaluation web form in iLearn.

- The response is visible only to staff, not other students or team members.
- The supplied guidance allows a five-day grace period after the group submission deadline.
- Individual contribution evidence can be used to individualise marks.

## Due date

For 2026, submit the group PDF through the Design Proposal submission box by **Sunday, 1 November 2026 at 23:55**. Complete the individual evaluation within the announced five-day window.

## Marking model

A2 is marked out of 100 and contributes 30% of the unit grade.

| Component | Marks |
| --- | ---: |
| Overall document clarity and presentation | 10 |
| System Design | 25 |
| Requirements traceability and functional allocation | 10 |
| Test Specification | 20 |
| Report to COMP2050 staff | 25 |
| Appendix items | 10 |
| **Total** | **100** |

## Qualitative marking guidance

### Professionalism and completeness

- Clear, high-quality writing, diagrams and figures.
- Current, relevant references and complete team information.
- Professional structure, appearance, language and tone for the target audience.
- Evidence of thoughtful and creative engagement beyond minimum compliance.

### Discussion and reflection

- Serious, evidence-based reflection written in a professional but natural voice.
- Useful exploration of alternatives, hypothetical consequences and decision rationales.

### Consistency

- Consistent terminology and identifiers across prose, architecture, diagrams, RTM, state diagrams and test cases.
- Components/modules retain the same names throughout the document.

### Teamwork

- Evidence of continuous, collaborative work rather than isolated pieces merged at the deadline.
- Balanced contribution rather than one person completing the work for everyone.
- Activity records and appendices show allocations, agreements, progress updates, problems, requests for help and team communication.

## Quality questions before submission

- Would a development team be able to plan implementation from this document?
- Does the design genuinely satisfy and trace to the received requirements?
- Are architecture and trade-offs technically coherent and well explained?
- Are difficult states, concurrency, data management, maintenance and deployment considered?
- Do tests cover the requirements, states and important edge cases?
- Are gaps in the received SRS handled through explicit, defensible assumptions?

## Related notes

- The current A1/A2 workflow and timeline in iLearn.
- The A1 submission and marking guide in the repository root.
- [A2 working-folder guide](README.md)
