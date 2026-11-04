# Solution Architecture

> Copy this file to the project's agreed architecture path (commonly
> `ARCHITECTURE.md`). Replace each `{{placeholder}}` with confirmed information,
> `unknown`, or `not applicable`; remove sections that do not fit. Link
> requirements using stable IDs from `PRODUCT.md` or its equivalent. Clearly
> distinguish the system that exists from a proposed design.

## Document control

- **System or project:** {{name}}
- **Purpose and audience:** {{purpose_and_audience}}
- **Architecture status:** {{current_proposed_or_mixed}}
- **Owner and reviewers:** {{roles_or_unknown}}
- **Last reviewed:** {{date_or_unknown}}
- **Requirements and related documents:** {{paths_or_unknown}}
- **Evidence and sources:** {{sources_or_unknown}}

## Executive overview

{{short_description_of_system_boundary_main_responsibilities_and_approach}}

- **Goals and design drivers:** {{outcomes_and_requirement_ids}}
- **In scope:** {{capabilities_and_responsibilities}}
- **Out of scope:** {{exclusions_and_external_ownership}}
- **Known limitations:** {{limitations_or_unknown}}

State which parts are implemented, proposed, or unconfirmed. Keep the design
proportional to confirmed requirements.

## Current situation

Describe the observed workflow, users, systems, data, and limitations. Cite
sources for material facts. Separate facts from suspected causes and unknowns.
If the design is entirely proposed, say so; do not describe proposed systems
as current state.

{{current_situation_and_evidence_or_unknown}}

## System boundary and context

Define the system's ownership boundary, users, external systems, and important
relationships. Keep external actors outside the system boundary. Identify
provisional integrations and the organization responsible for each side.

| Person or external system | Role and owner | Interaction and direction | Data or interface | Status and source |
| --- | --- | --- | --- | --- |
| {{actor_or_system}} | {{responsibility_and_owner}} | {{who_initiates_and_direction}} | {{data_contract_or_unknown}} | {{confirmed_or_provisional_source}} |

### Context diagram

{{diagram_path_or_not_created}} — {{question_answered_and_status}}

Show the named system boundary, people, external systems, and labeled,
directional relationships. Identify the diagram notation and validation status.

## Runtime and design elements

Describe the major elements and their responsibilities. Distinguish
independently running applications and data stores (containers) from internal
components, libraries, and third-party products. Include technology only when
selected or evidence-based; otherwise mark it as open.

| Element | Kind and boundary | Responsibility | Dependencies and interfaces | Technology | Status |
| --- | --- | --- | --- | --- | --- |
| {{element}} | {{container_component_external_or_other}} | {{responsibility}} | {{dependency_or_contract}} | {{known_choice_or_unknown}} | {{existing_proposed_or_unconfirmed}} |

### Container diagram

{{diagram_path_or_not_created}} — {{scope_question_and_status}}

Show the containers within the system boundary, their runtime responsibilities,
and directional, labeled relationships. Do not use the diagram to imply
unconfirmed technology or deployment choices.

## Important flows and interfaces

Describe each critical flow from trigger through outcome, including decision
points, failures, retries or recovery, and human handoffs. Name responsible
elements and show what crosses system and trust boundaries. Link to confirmed
contracts where available; mark unknown contracts explicitly.

| Flow | Trigger and sequence | Data and interface | Failure, recovery, and owner | Related requirements and status |
| --- | --- | --- | --- | --- |
| FLOW-1 | {{trigger_elements_decisions_and_outcome}} | {{data_and_contract}} | {{failure_path_recovery_and_responsible_owner}} | {{FR_or_NFR_ids_and_status}} |

## Data and trust boundaries

Document data ownership, sources of truth, classification, access, storage,
transformation, retention, deletion, and movement between trust zones. Explain
how derived data, logs, backups, and audit records link to source data and
versioned processing where applicable.

| Data set or class | Authority and owner | Access and movement | Storage and lifecycle | Protection and status |
| --- | --- | --- | --- | --- |
| {{data_class}} | {{source_of_truth_and_owner}} | {{who_can_access_and_interfaces}} | {{location_retention_deletion}} | {{controls_and_evidence}} |

## Security, privacy, and operations

Describe applicable controls and their evidence; do not claim compliance based
only on design intent. Include identity and authorization, secrets, encryption,
privacy, audit, monitoring, alerting, support ownership, deployment,
availability, backup, restore, recovery, and rollback as relevant.

| Concern | Design or control | Owner and dependency | Verification or operation | Status and evidence |
| --- | --- | --- | --- | --- |
| {{concern}} | {{approach_or_unknown}} | {{owner_or_dependency}} | {{test_measurement_or_operating_process}} | {{planned_unverified_or_evidence}} |

## Automation and agent boundaries

Complete this section when AI or other autonomous automation is used; otherwise
remove it. Define what the automation can observe, decide, and do. Identify
available data and tools, permission limits, independent policy enforcement,
human approval points, escalation paths, failure containment, and records
needed for audit or replay. Distinguish recommendations from executed actions.
Confidence scores, prompts, and logs alone do not establish safety,
correctness, or determinism.

| Action | Permitted scope and tool access | Enforcement and approval | Failure and escalation | Traceability and status |
| --- | --- | --- | --- | --- |
| {{action_or_recommendation}} | {{allowed_data_tools_and_limits}} | {{independent_policy_gate_or_human_approval}} | {{deny_retry_or_escalate_behavior}} | {{inputs_versions_decision_record_and_status}} |

## Quality attributes and requirement mapping

Map important requirements and quality attributes to design elements and
verification. Include measurable workload, environment, data, and acceptance
conditions; keep proposed checks separate from completed evidence.

| Requirement ID | Design element or flow | Design response | Validation conditions and method | Result and evidence |
| --- | --- | --- | --- | --- |
| {{FR_or_NFR_id}} | {{element_or_flow}} | {{approach_or_open_design}} | {{test_review_or_measurement}} | {{not_verified_or_evidence}} |

## Decisions and alternatives

Record significant decisions and their tradeoffs. Mark pending decisions and
identify who must make them. Do not present an unapproved proposal as selected.

| ID | Decision and context | Alternatives and tradeoffs | Outcome and rationale | Owner, date, and status |
| --- | --- | --- | --- | --- |
| ADR-1 | {{decision_needed}} | {{options_benefits_costs_and_risks}} | {{selected_option_or_pending}} | {{owner_date_status}} |

## Assumptions, risks, and open questions

| ID | Type | Statement and impact | Evidence or source | Validation or decision | Owner and status |
| --- | --- | --- | --- | --- | --- |
| R-1 | {{assumption_risk_or_question}} | {{statement_and_impact}} | {{evidence_or_unknown}} | {{next_action}} | {{owner_and_status}} |

## Architecture validation

Identify the next review or validation milestone, the participants, the
conditions for success, and the decision that follows. Record diagram source
and render checks when diagrams are used. Document limitations; do not claim
readiness or regulatory compliance without supporting evidence.

- **Next milestone:** {{milestone_or_unknown}}
- **Participants:** {{roles_or_unknown}}
- **Success conditions:** {{criteria_or_unknown}}
- **Decision and owner:** {{decision_and_owner_or_unknown}}
