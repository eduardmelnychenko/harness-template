# Product Requirements

> Template: copy this file to `PRODUCT.md` in the target project. Replace each
> `{{placeholder}}` with known information or `unknown`, and remove sections
> that do not apply. Adapt existing requirements instead of replacing them
> without approval. Use stable IDs to link requirements to acceptance criteria.
> Record the source and confirmation status of material statements; do not
> present assumptions, targets, or proposed capabilities as verified facts.

## Document context

- **Product or initiative:** {{name}}
- **Owner and stakeholders:** {{names_or_roles}}
- **Status and last reviewed:** {{draft_proposed_or_agreed; date}}
- **Sources:** {{customer_input_research_existing_documents_or_unknown}}
- **Related architecture or design:** {{path_or_not_yet_available}}

## Purpose and problem

- **Customer or organization:** {{who_has_the_need}}
- **Problem and why it matters:** {{observed_problem_and_impact}}
- **Current workflow:** {{how_work_is_done_today_including_workarounds}}
- **Evidence and baseline:** {{observations_sources_and_known_limits}}
- **Desired outcome:** {{what_should_improve_and_for_whom}}

Separate the observed problem from its suspected cause. Mark information that
still needs customer confirmation.

## Users and stakeholders

| User or stakeholder | Goals and responsibilities | Current pain points or needs | Source and status |
| --- | --- | --- | --- |
| {{role}} | {{goals}} | {{needs}} | {{source_and_confirmation}} |

## Outcomes and success measures

| Outcome | Baseline | Target | Measurement, population, and time frame | Owner | Source and status |
| --- | --- | --- | --- | --- | --- |
| {{outcome}} | {{baseline_or_unknown}} | {{target_or_unknown}} | {{how_and_when_to_measure}} | {{owner}} | {{source_and_confirmation}} |

Targets are desired results, not proof of performance. Record measured results
and their evidence separately when available.

## Scope

- **In scope:** {{workflows_capabilities_and_deliverables}}
- **Out of scope:** {{explicit_exclusions}}
- **Initial release or phase:** {{smallest_useful_scope_or_unknown}}
- **Product and organizational boundaries:** {{responsibilities_and_handoffs}}

## Workflows, data, and integrations

Describe the intended workflow, including who acts, what starts and ends the
workflow, important decisions, and exceptions. Avoid assuming systems or
interfaces that have not been confirmed.

| Input, output, or integration | Source or recipient | Purpose and format | Constraints or dependencies | Source and status |
| --- | --- | --- | --- | --- |
| {{item}} | {{source_or_recipient}} | {{purpose_and_format_or_unknown}} | {{constraints_or_unknown}} | {{source_and_confirmation}} |

## Functional requirements

State observable behavior and who needs it; avoid prescribing an implementation
unless it is a confirmed constraint.

| ID | User or actor | Requirement | Priority | Source and status | Acceptance criteria IDs |
| --- | --- | --- | --- | --- | --- |
| {{FR-1}} | {{role}} | {{observable_behavior}} | {{priority}} | {{source_and_confirmation}} | {{AC-1}} |

## Non-functional requirements

For each applicable quality requirement, specify a measurable target and the
conditions under which it is measured. Consider security, privacy,
accessibility, performance, reliability, usability, maintainability,
interoperability, operations, and compliance where relevant; do not assume any
particular standard or obligation applies.

| ID | Quality attribute | Requirement and target | Measurement conditions | Source and status | Acceptance criteria IDs |
| --- | --- | --- | --- | --- | --- |
| {{NFR-1}} | {{attribute}} | {{measurable_requirement_or_unknown}} | {{workload_environment_or_unknown}} | {{source_and_confirmation}} | {{AC-2}} |

## Constraints and dependencies

| ID | Constraint or dependency | Source or owner | Impact on scope or delivery | Status |
| --- | --- | --- | --- | --- |
| {{C-1}} | {{environment_data_security_legal_budget_timeline_or_other}} | {{source_or_owner}} | {{impact}} | {{confirmed_or_unconfirmed}} |

## Deliverables

| Deliverable | Audience and format | Scope or related requirement IDs | Owner | Status |
| --- | --- | --- | --- | --- |
| {{deliverable}} | {{audience_and_format}} | {{scope_or_ids}} | {{owner}} | {{status}} |

## Acceptance criteria

Define testable conditions for both deliverables and product behavior. For each
criterion, identify the verification method and who accepts the result.

| ID | Requirement or deliverable | Observable criterion | Verification method and evidence | Acceptance owner | Status |
| --- | --- | --- | --- | --- | --- |
| {{AC-1}} | {{FR-1}} | {{given_conditions_when_action_then_expected_result}} | {{test_review_or_other_check}} | {{owner}} | {{not_verified_or_result}} |
| {{AC-2}} | {{NFR-1}} | {{measurable_target_under_defined_conditions}} | {{measurement_or_other_check}} | {{owner}} | {{not_verified_or_result}} |

## Assumptions, risks, and open questions

| Type | Statement and impact | Evidence or source | Validation or decision needed | Owner | Status |
| --- | --- | --- | --- | --- | --- |
| {{assumption_risk_or_question}} | {{statement_and_impact}} | {{evidence_or_unknown}} | {{next_step}} | {{owner_or_unknown}} | {{status}} |

## Validation and delivery plan

| Milestone or experiment | What it will validate | Participants | Success criteria and next decision | Timing | Status |
| --- | --- | --- | --- | --- | --- |
| {{milestone}} | {{hypothesis_or_scope}} | {{participants}} | {{criteria_and_decision}} | {{date_or_unknown}} | {{status}} |

Distinguish discovery, prototype, and production work when applicable. Update
requirements and related design documents when decisions are confirmed; record
remaining limitations and do not claim compliance or readiness without evidence.
