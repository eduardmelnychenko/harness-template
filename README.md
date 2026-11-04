# harness-template

A small set of Markdown templates for giving AI coding agents clear project
context, requirements, and architecture guidance. Copy the templates you need
into a project, replace the placeholders with confirmed information, and adapt
or remove sections that do not apply.

## Templates

| File | Copy to | Purpose |
| --- | --- | --- |
| `AGENT.template.md` | `AGENT.md` | Project-specific working instructions, startup steps, conventions, verification, and definition of done. |
| `PRODUCT.template.md` | `PRODUCT.md` | Product purpose, users, scope, requirements, acceptance criteria, assumptions, and delivery plan. |
| `ARCHITECTURE.template.md` | `ARCHITECTURE.md` | System boundaries, design elements, flows, operations, decisions, risks, and validation. |

These are starting points, not filled-in project specifications. You can use
them independently; the agent-instructions template is designed to link to
`PRODUCT.md` and `ARCHITECTURE.md` when those documents are used.

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

1. Replace each `{{placeholder}}` with confirmed project information or
   `unknown`; remove sections that are not relevant.
2. Record sources and distinguish confirmed facts from proposals, assumptions,
   targets, and items that still need validation.
3. Keep requirement and acceptance-criteria IDs consistent across the product
   and architecture documents.
4. Update `AGENT.md` to point to the documents and project-specific setup,
   verification commands, and conventions that actually exist.
5. Review the result with the project team and keep it current as decisions
   change.

If the target project already has instructions or documentation, adapt those
documents rather than replacing them without approval. Do not treat template
text as a project decision or claim that a requirement, check, or control is
verified without evidence.

## Repository contents

This repository contains Markdown templates, example project documents, and
this README. It does not include a runnable application or setup, build, or
test commands.
