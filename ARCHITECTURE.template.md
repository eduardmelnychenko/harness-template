# Solution Architecture

> Template: copy this file to `ARCHITECTURE.md` in the target project. Replace
> each `{{placeholder}}` with known information or `unknown`, and remove
> sections that do not apply. Adapt existing architecture documents instead of
> replacing them without approval. Use the requirements and acceptance IDs from
> `PRODUCT.md` or the project's equivalent requirements document.
>
> Distinguish the existing system from proposed designs. Record sources,
> assumptions, and confirmation status; do not present targets, proposed
> capabilities, or compliance as verified facts.

## Document context

- **Project or system:** {{name}}
- **Purpose and audience:** {{purpose_and_audience}}
- **Architecture status:** {{existing_proposed_or_mixed}}
- **Owner, stakeholders, and last reviewed:** {{roles_and_date}}
- **Requirements and related documents:** {{paths_or_unknown}}
- **Sources and evidence:** {{sources_or_unknown}}

## Goals and design drivers

Summarize the customer outcome, key requirements, and constraints that shape
the architecture. Use stable IDs from the requirements document where available.

| Requirement or constraint ID | Design driver and rationale | Source and status |
| --- | --- | --- |
| {{requirement_or_constraint_id}} | {{goal_or_constraint_and_impact}} | {{source_and_confirmation}} |

## Current situation

Describe the existing workflow, users, systems, data, and relevant limitations
when known. Separate observed facts from suspected causes and unknowns. Do not
invent current systems or interactions to complete this section.

{{current_situation_or_unknown}}

State the evidence or source for material facts. If the architecture is entirely
proposed, say so and avoid presenting proposed components or integrations as
part of the existing system.

## Solution overview and scope

- **Proposed or existing approach:** {{summary_and_rationale}}
- **System boundary and ownership:** {{boundary_and_responsibilities}}
- **In scope:** {{included_capabilities_and_handoffs}}
- **Out of scope:** {{exclusions_and_external_responsibilities}}
- **Known limitations:** {{limitations_or_unknown}}

Identify which parts already exist and which are proposed or need confirmation.
Keep the design proportional to the problem and confirmed constraints.

## Diagrams

Link to diagram sources when they help the intended audience. Use the project's
established format and the narrowest useful level of detail. If using C4,
identify the level and scope; show clear system boundaries, named elements, and
directional, labeled relationships. Keep external actors outside the boundary.
Show the system boundary and distinguish people, external systems, and internal
elements. Label important flows with their purpose or data; include a legend
when notation needs explanation. Do not add detail that the audience cannot
validate or use.
Render and inspect diagrams when tooling allows, and record any limitations;
do not claim a visual check was performed unless it was.

| Diagram and source path | Level and scope | Question answered | Status and validation |
| --- | --- | --- | --- |
| {{name_and_path_or_not_created}} | {{context_container_or_other_scope}} | {{purpose}} | {{status_and_checks}} |

## System context

Describe external people and systems, their responsibilities, and their
relationships to the system. Mark unconfirmed integrations as provisional.

| External person or system | Role | Interaction and direction | Data or interface | Source and status |
| --- | --- | --- | --- | --- |
| {{actor_or_system}} | {{responsibility}} | {{interaction_and_direction}} | {{data_or_interface_or_unknown}} | {{source_and_confirmation}} |

## Design elements and responsibilities

Describe the major parts within the boundary, their responsibilities, and their
dependencies. For a C4 container view, a container is an independently running
application or data store, not necessarily a particular deployment technology.
Distinguish deployable/runtime containers from internal components, libraries,
and third-party services. Record selected technologies only when they are
known, and add component-level detail only when it is useful for the task.

| Element | Responsibility | Dependencies or interfaces | Technology or format | Status |
| --- | --- | --- | --- | --- |
| {{element}} | {{responsibility}} | {{dependencies_or_unknown}} | {{choice_or_unknown}} | {{existing_proposed_or_unconfirmed}} |

## Main flows and interfaces

Describe the main workflows in order, including triggers, inputs, outputs,
decisions, and relevant failure or recovery paths. Name the responsible
elements, direction of data flow, and trust or approval boundaries. Use
confirmed interface names and contracts; mark unknown interfaces, ownership,
and recovery behavior explicitly.

1. {{trigger_and_first_step}}
2. {{subsequent_steps_and_outcome}}
3. {{exceptions_or_recovery_when_applicable}}

| Source and destination | Purpose and data | Interface or contract | Failure handling | Status |
| --- | --- | --- | --- | --- |
| {{source_to_destination}} | {{interaction_and_data}} | {{contract_or_unknown}} | {{handling_or_unknown}} | {{source_and_confirmation}} |

## Data and operations

Document applicable data ownership, access, storage, lifecycle, retention, and
deletion requirements. Describe deployment environments and operational
ownership, including monitoring, support, backup, recovery, and rollback where
relevant. Identify dependencies and distinguish planned, implemented but
unverified, and validated controls. Preserve source data and provenance where
required; state how derived data, logs, and audit records relate to their
inputs and versions.

| Area | Design or operational approach | Owner or dependency | Source and status |
| --- | --- | --- | --- |
| {{data_deployment_or_operations_area}} | {{approach_or_unknown}} | {{owner_or_dependency_or_unknown}} | {{source_and_confirmation}} |

## Automation and agent boundaries

Complete this section when the system uses an AI agent or other autonomous
automation; otherwise remove it. Describe the automation's bounded role, the
data and tools it can access, and which actions require human approval.
Distinguish recommendations from actions and identify the component that
independently enforces permissions and policy. Document execution limits,
failure handling, escalation, and traceability. Do not assume that confidence
scores, prompts, or recorded decisions alone make an action safe or repeatable.

| Action or capability | Allowed scope and controls | Approval or escalation | Evidence and versioning | Status |
| --- | --- | --- | --- | --- |
| {{action_or_capability}} | {{permissions_limits_and_policy}} | {{human_or_policy_gate}} | {{inputs_tools_models_and_records}} | {{source_and_confirmation}} |

## Cross-cutting requirements

Address applicable security, privacy, accessibility, performance, scalability,
reliability, interoperability, maintainability, observability, and compliance
requirements. Include automation permissions, human oversight, and fallback
paths where applicable. Do not assume a particular standard or obligation.

| Requirement ID or quality attribute | Proposed or existing approach | Conditions and validation needed | Status |
| --- | --- | --- | --- |
| {{NFR-1}} | {{design_or_control}} | {{measurement_or_review_needed}} | {{status_and_evidence_or_unknown}} |

## Decisions and alternatives

| Decision ID | Options and tradeoffs | Decision and rationale | Owner, date, and status |
| --- | --- | --- | --- |
| {{decision_id}} | {{alternatives_value_effort_and_risk}} | {{decision_and_reason_or_pending}} | {{owner_date_and_status}} |

## Assumptions, risks, and open questions

| Type | Statement and impact | Evidence or source | Validation or decision needed | Owner | Status |
| --- | --- | --- | --- | --- | --- |
| {{assumption_risk_or_question}} | {{statement_and_impact}} | {{evidence_or_unknown}} | {{next_step}} | {{owner_or_unknown}} | {{status}} |

## Validation and acceptance

Map important requirements and acceptance criteria to design elements and a
verification method. Record workload, environment, test data, and acceptance
conditions as needed. Separate planned checks from results and link evidence
only for checks actually performed.

| Requirement ID | Acceptance ID | Design element | Validation method and conditions | Result, evidence, and status | Owner |
| --- | --- | --- | --- | --- | --- |
| {{FR-1}} | {{AC-1}} | {{element_or_flow}} | {{test_review_or_other_check}} | {{not_verified_or_evidence}} | {{owner}} |
| {{NFR-1}} | {{AC-2}} | {{element_or_control}} | {{measurement_or_other_check}} | {{not_verified_or_evidence}} | {{owner}} |

Identify the next validation milestone, participants, success criteria, and
decision point: {{validation_plan_or_unknown}}. Document unresolved gaps and
do not claim readiness or compliance without supporting evidence.
