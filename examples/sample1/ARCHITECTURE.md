# Proposed Solution Architecture

## Status and scope

This document describes a proposed solution for company X. It is not a
description of an existing system or a claim that the solution meets the
requirements. The requirements are in `PRODUCT.md`.

The proposed agent-based solution receives DICOM studies, annotations and
metadata. It checks them for errors, proposes or applies corrections, and
supports human review. It provides the resulting data and reports to company X.

The architecture is provisional. The imaging modalities, annotation formats,
integration interfaces, deployment environment and operating procedures need
confirmation.

The [current situation diagram](current-situation.drawio) shows the existing
company-level workflow and the stated data-quality issue. It does not describe
the proposed system or assume current software systems or transfer methods.

The customer presentation uses four views from
[presentation-diagrams.drawio](presentation-diagrams.drawio): the current
situation, the proposed solution layers, the bounded agent workflow, and a
selected container-level view of the tools block. These presentation views do
not replace the detailed C4 diagrams below. The tools view lists check
categories, not selected products or separate deployable containers.

## System context

**System boundary:** the proposed image-data quality system operated for
company X. The [system context diagram](system-context.drawio) shows the
proposed system, external users and systems, and their relationships.

| External person or system | Relationship to the proposed system |
| --- | --- |
| Company Y data source | Supplies imaging datasets, annotations and metadata through an agreed interface. |
| Company X reviewer | Reviews detected issues and approves, rejects or modifies proposed corrections. |
| Company X operational and management users | View processing status, quality metrics and reports according to their roles. |
| Company X downstream systems and users | Receive processed data and reports through agreed interfaces. |
| Enterprise identity provider | Authenticates users when enterprise integration is available. |
| Storage and enterprise systems | Exchange data with the solution through authorized interfaces, including existing AWS S3 storage where applicable. |

Company Y's internal processing is outside the system boundary. The solution
does not assume direct access to company Y's systems.

## Container-level design

The [container diagram](container-diagram.drawio) has two complementary pages
for selected processing and delivery flows, and review and reporting flows.
Repeated containers represent the same logical containers. The following
containers, their deployment boundaries, technology choices and interfaces
require validation.

| Container | Responsibility |
| --- | --- |
| Ingestion and job management | Accept batches, check their manifest and inputs, record their provenance, and track processing state. |
| AI agent orchestration | Select and coordinate approved validation tools for each batch, interpret their results, and submit findings and proposed actions for independent policy evaluation. |
| Validation and analysis workers | Check DICOM data, metadata, labels and masks; run configured rules and AI analysis; record findings and confidence scores. |
| Correction and review service | Independently enforce approved correction policies, apply eligible corrections, create review tasks, and record reviewer decisions and corrections. |
| Review and reporting interface | Present work queues, findings, explanations, correction suggestions, status and reports to authorized users. |
| Reporting service | Produce validation, quality, processing, audit and correction-history reports from recorded results. |
| Source and result storage | Store original inputs separately from versioned derived outputs and reports. |
| Operational data store | Store job state, findings, review tasks, decisions, configurations and references to stored data. |
| Audit store | Retain a protected, immutable history of processing and user actions. |
| Integration interface | Deliver authorized results and reports to company X systems using agreed contracts. |

The agent orchestration, workers and inference capacity should scale
horizontally. Storage should scale independently of processing. Deployment
choices must support cloud, hybrid and on-premises environments; integration
with AWS S3 is required where company X uses it, but S3 is not assumed to be
available in every environment.

## Agent role and boundaries

The proposed AI agent is a separate orchestration container, not a synonym
for an image-analysis model. For an accepted batch, it receives dataset
references and permitted processing context, selects from approved tools,
invokes validation and analysis workers, and interprets their results. It
submits findings, supporting evidence, confidence information and proposed
actions to the correction and review service. The workers and configured
validation rules remain responsible for their specific checks.

The agent may select and sequence only tools and actions permitted by
company X's approved configuration. Tool calls use authorized access and
bounded execution, with limits and failure handling to be defined and
validated. The agent cannot directly modify source data, approve its own
corrections or bypass the correction and review service. That service
independently checks the correction type, policy, evidence and confidence
against approved criteria before applying a correction. Uncertain,
ineligible, invalid or insufficiently supported cases go to human review.
Thresholds, allowed actions, model and tool choices, and failure handling
remain open decisions.

Agent decisions and tool calls must be traceable alongside dataset, model,
tool, rule, configuration and policy versions. Audit records must include
the evidence and the automated or human decision, subject to company X's
privacy and retention policies. Data access and any model hosting or external
data transfer require security and privacy approval; an external model
provider is not assumed.

Recording versions and inputs enables investigation and replay, but does not
by itself make agent planning deterministic. Deterministic validation and
repeatable outcomes for the same dataset and model version remain product
requirements. The selected tools, agent behavior and execution environment
must be tested against that requirement; how to meet it remains an open
design decision.

## Main processing flow

1. Company Y supplies a batch through an agreed interface. Ingestion records
   the source and input versions and stores the original data without
   overwriting it.
2. Job management starts the agent workflow with dataset references. The
   agent selects approved tools; validation and analysis workers check the
   data and return findings, explanations and confidence scores.
3. The agent submits evidence and proposed actions to the correction and
   review service. The service independently evaluates them against versioned
   rules and policies. It applies only corrections permitted by an approved
   high-confidence policy and sends uncertain or ineligible cases for review.
4. Reviewers approve, reject or modify suggestions. The correction and review
   service records and applies authorized decisions according to policy,
   preserves the relationship between original and derived data, and updates
   the job state for continued processing or delivery.
5. The system stores versioned results and makes authorized outputs and
   reports available to company X. It records processing and review actions in
   the audit trail.

The confidence thresholds, eligible correction types, review criteria and output
contracts require company X approval. A confidence score alone must not be
treated as proof that a correction is safe or accurate.

## Cross-cutting design

- **Reliability:** retain source data separately from derived outputs; record
  job checkpoints and isolate failed records so other records can continue.
  Recovery, backup and restore procedures must be validated before production.
- **Repeatability:** record input, rule, model and configuration versions for
  each result. Validate repeatability for the selected models and runtime;
  deterministic behavior is a requirement, not an established capability.
- **Security and privacy:** encrypt data in transit and at rest; enforce
  authenticated and authorized access, role-based permissions, and managed
  secrets. Apply company X policies for patient data, retention and deletion.
- **Auditability:** record automated and manual actions with data provenance,
  model and rule versions, decisions and timestamps. The audit store must
  support immutable retention and authorized access.
- **Operations:** expose job progress, logs, metrics and alerts for failures,
  SLA breaches and abnormal behavior. Design for recovery from transient
  failures and high availability of critical services.
- **AI governance:** version models and control their deployment. Measure
  detection and correction performance on representative, reviewed data.
  Escalate cases outside approved automated correction policies.

## Validation and open decisions

The following targets are requirements, not verified outcomes: at least
10,000 studies per day, 99.9% availability, reviewer response times under
three seconds for common operations, at least 95% error detection accuracy
and at least 90% automated correction precision. The workload, measurement
methods, test data and acceptance procedures must be agreed before these
targets can be verified.

Key decisions and inputs still needed:

- Imaging modalities, study sizes, volumes and peak arrival patterns.
- Annotation and mask formats, expected anatomy, label vocabulary, and
  authoritative sources for metadata and validation rules.
- Current workflow, representative errors, and the basis of the estimated
  10% incorrect information. The unit of that estimate is not specified.
- Input and output interfaces, existing AWS and enterprise integrations, and
  the target deployment environment.
- Permitted automated correction types, confidence thresholds, reviewer roles,
  escalation procedures and ownership of final decisions.
- Agent models, approved tools and execution limits; independent policy
  enforcement; replay and deterministic-outcome validation.
- Definitions and evaluation datasets for detection accuracy and correction
  precision, including performance across relevant data groups.
- Applicable regulatory obligations, data residency, retention, access,
  audit immutability and recovery requirements.
- Availability measurement, SLA targets, review workload, infrastructure
  capacity and operational ownership.

Before production, validate the architecture and model behavior with company X
and its relevant clinical, quality, privacy, security and operations
stakeholders. The architecture alone does not establish regulatory compliance.
