# harness-template

A small set of Markdown templates for giving AI coding agents clear project
context, requirements, and architecture guidance. Each template is a complete
starting document: copy it into a project, fill in confirmed information, and
remove sections that do not apply.

## Templates

| File | Copy to | Purpose |
| --- | --- | --- |
| `AGENT.template.md` | `AGENTS.md` or `AGENT.md` | Project-specific working instructions, startup steps, conventions, verification, and definition of done. |
| `PRODUCT.template.md` | `PRODUCT.md` | Product purpose, users, scope, requirements, acceptance criteria, assumptions, and delivery plan. |
| `ARCHITECTURE.template.md` | `ARCHITECTURE.md` | System boundaries, design elements, flows, operations, decisions, risks, and validation. |

The templates are designed to work together but can be used independently.
`AGENT.template.md` links to project requirements and architecture when
available. Product requirement IDs should be reused in architecture and
acceptance records when the documents are used together.

## Examples

The `examples/` folder shows the templates applied to two different scenarios.
Use the examples to see how to record concrete workflows, trace requirements
to acceptance criteria and design, distinguish current facts from proposed
architecture, and define boundaries for agent-driven actions. Example-specific
details are illustrative, not defaults or requirements for other projects.

## Getting started

From this repository's root, copy the templates you want into the target
project:

```sh
cp PRODUCT.template.md /path/to/project/PRODUCT.md
cp ARCHITECTURE.template.md /path/to/project/ARCHITECTURE.md
cp AGENT.template.md /path/to/project/AGENT.md
```

Then customize the copied files:

1. Replace each `{{placeholder}}` with confirmed information, `unknown`, or
   `not applicable`; remove sections that do not fit.
2. Cite sources for important statements and distinguish observed facts,
   approved decisions, assumptions, proposals, targets, and verified results.
3. Keep requirement IDs and acceptance links stable across documents.
4. Add only project-confirmed commands, technologies, integrations, policies,
   and controls. Mark unresolved choices clearly.
5. Review the documents with their owners and update them when requirements or
   design decisions change.

If the target project already has instructions or documentation, adapt those
documents rather than replacing them without approval. Do not treat template
text as a project decision or claim that a requirement, check, or control is
verified without evidence.

## Repository contents

This repository contains Markdown templates, example project documents, and
this README. It does not include a runnable application or project-specific
setup, build, or test commands.
