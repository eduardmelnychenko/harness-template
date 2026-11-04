# Product Requirements

> Copy this file to the project's agreed requirements path (commonly
> `PRODUCT.md`). Replace each `{{placeholder}}` with confirmed information,
> `unknown`, or `not applicable`; remove sections that do not fit. Keep
> assumptions and proposals distinct from agreed requirements. Use stable IDs
> so requirements, acceptance criteria, and architecture can refer to each
> other.

## Document control

- **Product or initiative:** {{name}}
- **Document owner:** {{role_or_name}}
- **Contributors and decision-makers:** {{roles_or_unknown}}
- **Status:** {{draft_proposed_agreed_or_other}}
- **Last reviewed:** {{date_or_unknown}}
- **Sources:** {{interviews_research_existing_documents_or_unknown}}
- **Related documents:** {{paths_or_unknown}}

## Summary

- **For whom:** {{primary_customer_or_user}}
- **Need or problem:** {{observed_problem_and_impact}}
- **Proposed outcome:** {{change_expected_for_users}}
- **Evidence:** {{source_and_limits_of_evidence}}

Separate observed facts from suspected causes and desired outcomes. Mark
unconfirmed statements and do not present a proposed solution as an agreed
product decision.

## Users and stakeholders

| User or stakeholder | Goals and responsibilities | Needs, constraints, or pain points | Source and status |
| --- | --- | --- | --- |
| {{role}} | {{goals_and_responsibilities}} | {{needs_or_unknown}} | {{source_and_confirmation}} |

Include affected users, decision-makers, operators, support teams, and
dependent organizations where relevant. Identify who owns important handoffs
and decisions.

## Outcomes and measures

| ID | Outcome | Baseline | Target | Measure, population, and period | Owner and source |
| --- | --- | --- | --- | --- | --- |
| OUT-1 | {{user_or_business_outcome}} | {{value_or_unknown}} | {{target_or_unknown}} | {{unit_method_population_period}} | {{owner_source_status}} |

Targets are desired results, not measured performance. Define the unit,
population, workload, conditions, and time period. Record measured results and
their evidence separately.

## Scope and delivery

- **In scope:** {{capabilities_workflows_and_deliverables}}
- **Out of scope:** {{explicit_exclusions}}
- **Initial release or phase:** {{smallest_useful_delivery_or_unknown}}
- **Product boundary:** {{responsibilities_and_external_handoffs}}
- **Dependencies:** {{teams_systems_data_or_unknown}}

| Milestone | Deliverable | Audience and format | Owner | Exit condition and status |
| --- | --- | --- | --- | --- |
| {{phase_or_date}} | {{artifact_or_capability}} | {{audience_and_format}} | {{owner}} | {{observable_exit_condition}} |

## Users, workflows, and information

Describe the main user journeys from trigger to outcome. Include decisions,
exceptions, recovery, and who acts at each handoff. Keep the current workflow
separate from the desired workflow.

| Flow ID | Actor and trigger | Main steps and decisions | Outcome and exception paths | Source and status |
| --- | --- | --- | --- | --- |
| FLOW-1 | {{actor_and_trigger}} | {{steps_and_decisions}} | {{outcome_failures_and_recovery}} | {{source_and_confirmation}} |

| Information or integration | Source and recipient | Purpose, format, and authority | Sensitivity, retention, or constraint | Source and status |
| --- | --- | --- | --- | --- |
| {{data_or_interface}} | {{producer_and_consumer}} | {{purpose_format_authority}} | {{constraints_or_unknown}} | {{source_and_confirmation}} |

Identify authoritative sources, ownership, relevant data quality, privacy,
retention, deletion, and interface dependencies when known. Do not assume an
integration or data contract that has not been confirmed.

## Functional requirements

Write observable outcomes, not implementation instructions, unless a
technology or design is a confirmed constraint. Use one stable ID per
requirement. Keep independent behaviors separate. Define a priority scheme and
apply it consistently.

| ID | Actor | Requirement | Priority | Source and status | Acceptance IDs |
| --- | --- | --- | --- | --- | --- |
| FR-1 | {{user_or_system}} | {{single_observable_behavior}} | {{must_should_could_or_defined_scale}} | {{source_and_confirmation}} | {{AC-1}} |

**Priority definitions:** {{define_priority_values_and_release_implications}}

## Quality requirements and constraints

Include applicable security, privacy, safety, accessibility, performance,
reliability, availability, scalability, usability, maintainability,
interoperability, operations, and compliance needs. Do not assume a standard
or regulation applies without a source. Separate mandatory constraints from
targets and define how each target will be measured.

| ID | Attribute or constraint | Requirement or target | Measurement conditions | Source and status | Acceptance IDs |
| --- | --- | --- | --- | --- | --- |
| NFR-1 | {{quality_attribute}} | {{measurable_target_or_required_control}} | {{workload_environment_method_and_threshold}} | {{source_and_confirmation}} | {{AC-2}} |

| ID | Dependency or external constraint | Owner or source | Impact and required decision | Status |
| --- | --- | --- | --- | --- |
| C-1 | {{constraint_or_dependency}} | {{owner_or_source}} | {{impact_and_needed_action}} | {{confirmed_or_open}} |

## Acceptance criteria

Define conditions that can be observed and verified. Link each criterion to
requirements or deliverables. State test data, environment, workload, and
acceptance owner where needed. Separate the planned verification method from
the result; mark criteria met only when evidence exists.

| ID | Requirement or deliverable | Observable pass condition | Verification method and conditions | Evidence and status | Acceptance owner |
| --- | --- | --- | --- | --- | --- |
| AC-1 | FR-1 | {{given_when_then_or_equivalent_condition}} | {{test_review_measurement_and_conditions}} | {{not_verified_or_evidence}} | {{role}} |

## Assumptions, risks, and open questions

| ID | Type | Statement and impact | Evidence or source | Decision or validation needed | Owner and status |
| --- | --- | --- | --- | --- | --- |
| Q-1 | {{assumption_risk_or_question}} | {{statement_and_impact}} | {{evidence_or_unknown}} | {{next_step_or_decision}} | {{owner_and_status}} |

Prioritize questions that block scope, acceptance, safety, privacy, or delivery.
Do not silently convert assumptions into confirmed requirements.

## Validation and release plan

| Milestone or experiment | Hypothesis or requirement | Participants and environment | Success condition and decision | Timing and status |
| --- | --- | --- | --- | --- |
| {{milestone}} | {{what_will_be_validated}} | {{who_where_and_with_what_data}} | {{threshold_and_next_decision}} | {{date_and_status}} |

Distinguish discovery, prototype, pilot, and production when relevant. Record
remaining limitations and do not claim readiness, compliance, or performance
without supporting evidence.
