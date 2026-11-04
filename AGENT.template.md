# Agent Working Instructions

> Template: copy this file to `AGENT.md` in the target project. Replace each
> `{{placeholder}}` with project-specific information or `unknown`; remove
> sections that do not apply. Adapt existing instructions instead of replacing
> them without approval. Higher-priority instructions and the user's request
> take precedence over this file.

## Project context

- **Project:** {{project_name}}
- **Purpose and deliverables:** {{brief_description_or_link}}
- **Product requirements:** {{product_document_path; normally PRODUCT.md}}
- **Architecture and design:** {{architecture_document_path_or_not_used}}
- **Feature tracker:** {{feature_tracker_path_or_not_used}}
- **Work history:** {{history_document_path_or_not_used}}
- **Other project instructions:** {{paths_or_not_used}}

## Startup

Before starting work:

1. Read this file, the product requirements, and applicable architecture and
   task-specific instructions. Read the feature tracker and work history if
   they are used and relevant to the task. Treat history as context, not as a
   substitute for the current source files.
2. Identify the requested outcome, affected files, relevant acceptance
   criteria, and existing conventions. Check the working tree when applicable;
   preserve unrelated user changes.
3. If required information is missing, empty, invalid, or contradictory, do
   not invent it. Report the gap and continue only if it does not prevent safe,
   correct work. Ask for clarification when the gap blocks progress.
4. If a feature tracker is in use, preserve malformed data unchanged. Initialize
   a missing or empty tracker only when project instructions require it and the
   documented requirements, applicable architecture, and established schema
   are sufficient to do so without guessing. Otherwise report the gap.

## Boundaries and execution

- Keep work within the requested scope and confirmed requirements. Avoid
  unnecessary features, dependencies, and changes to unrelated behavior.
- Break complex work into manageable units, but complete the requested scope
  unless the user or a higher-priority instruction sets a limit.
- Follow established architecture, naming, formatting, and dependency patterns.
  Reuse existing code and checks when appropriate.
- Do not expose credentials, secrets, or private data in files, logs, examples,
  or responses. Do not perform destructive or external actions without explicit
  authorization.
- Investigate before asking questions. Ask when requirements conflict or an
  unresolved decision could materially change the result; otherwise state
  necessary assumptions and distinguish them from confirmed facts.
- Keep requirements, proposed designs, and verified behavior distinct. Mark
  unconfirmed choices, targets, compliance claims, and limitations clearly.

## Project conventions and verification

- **Languages, frameworks, and dependencies:** {{project_stack_or_unknown}}
- **Setup and build commands:** {{commands_or_not_applicable}}
- **Relevant test and lint commands:** {{commands_or_not_applicable}}
- **Document, diagram, or other artifact checks:** {{checks_or_not_applicable}}
- **Project-specific skills, formats, and conventions:** {{details_or_not_applicable}}

Run checks appropriate to the changed work and its acceptance criteria. For
visual artifacts, check both the file structure and the rendered result when
applicable. Investigate failures caused by the change; report unrelated
baseline failures, checks not run, and the reasons. Do not claim a check passed
unless it was actually run.

## Feature tracking

Use this section only if the project tracks features. Preserve the existing
tracker schema, statuses, and entries. Add or update entries only when the
requirements and project conventions support the change; do not delete existing
entries without authorization.

If the project has adopted the following statuses, use them as follows; otherwise
use the project's established status definitions:

- `not-started`: work has not started.
- `pass`: all applicable acceptance and done conditions are met, with evidence.
- `fail`: requirements or validation are not met; record the reason and
  remaining work.
- `blocked`: work cannot proceed; record the blocker and what is needed.

Never mark an item as passed based only on implementation, a target, or an
unverified assumption. Record the evidence and validation method in the tracker
when its schema supports them.

## Work history

If the project uses a history document, append a dated entry after each completed
work unit. Include the work and files changed, checks and their actual outcomes,
checks not run and why, and relevant decisions, blockers, or follow-up. Preserve
earlier entries; append corrections instead of rewriting history. Do not include
secrets or private data.

## Definition of done

- The requested work meets applicable confirmed requirements and acceptance
  criteria, and changed artifacts meet their format and language requirements.
- Relevant checks have been run and task-related failures resolved, or any
  remaining limitations are clearly reported.
- Documentation reflects changed behavior. Applicable feature status and
  evidence, and work history, are updated according to project conventions.
- The final response summarizes the changes, validation, and any remaining
  limitations or blockers; suggest a next step when useful.
