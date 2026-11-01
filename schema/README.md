# Evidence Schema and Provenance Mechanism v0.1

This directory provides Deliverable 2 from the practicum proposal: a reusable JSON Schema set for the records used by the evidence-grounded correlation framework. The schema keeps direct observations separate from later analytical and risk decisions.

## Record types

| Record type | Stable ID | Purpose |
|---|---|---|
| Assessment context | `A-...` | Identifies the target, scope, deployment context, and threat actors. |
| Artifact | `AR-....` | Identifies immutable or derived source material with path, hash, source metadata, and size. |
| Evidence | `E-....` | Records an observation, source locator, collection context, provenance, and interpretation boundary. |
| Hypothesis | `H-....` | Connects evidence to a testable security assertion, threat context, uncertainty, and recommended tests. |
| Validation test | `T-....` | Records a bounded test objective, procedure, preconditions, expected outcomes, and returned evidence references. |
| Finding | `F-....` | Records a supported, analyst-adjudicated technical finding and its demonstrated boundary. |
| Risk rationale | `R-....` | Records deployment-sensitive risk reasoning tied to one or more findings. |

## Design rules

- Evidence records state observations. They do not encode vulnerability conclusions.
- Artifact IDs, evidence IDs, and source locators let a reviewer trace an assertion to its supporting material.
- Hypothesis and test records preserve uncertainty and planned decision criteria before device interaction.
- Returned test evidence can support, narrow, contradict, or leave a hypothesis unvalidated.
- Finding and risk records remain separate so technical impact, attacker access, and deployment context are visible.
- Sensitive raw material belongs outside this public release. A public derivative must state its handling boundary and preserve its relation to the protected source when possible.

## Schema files

The JSON Schema files use the JSON Schema 2020-12 declaration and can be reused or extended for another assessment.

- [`json_schemas/assessment.schema.json`](json_schemas/assessment.schema.json)
- [`json_schemas/artifact.schema.json`](json_schemas/artifact.schema.json)
- [`json_schemas/evidence.schema.json`](json_schemas/evidence.schema.json)
- [`json_schemas/hypothesis.schema.json`](json_schemas/hypothesis.schema.json)
- [`json_schemas/validation_test.schema.json`](json_schemas/validation_test.schema.json)
- [`json_schemas/finding.schema.json`](json_schemas/finding.schema.json)
- [`json_schemas/risk_rationale.schema.json`](json_schemas/risk_rationale.schema.json)

## Implemented Archer C9 instance

The completed local Archer C9 assessment uses this v0.1 schema for its formal machine-readable instance. The full instance remains local because it references protected original material and restricted validation artifacts. The published [`../evidence-records/`](../evidence-records/) directory provides selected citation-safe evidence records that demonstrate the evidence-record structure and exact locators. The published assessment records demonstrate the later hypothesis, finding, and risk portions of the chain.

## Scope

This schema supports a reviewable assessment workflow. It does not itself establish legal chain of custody, determine exploitability, calculate severity, or replace analyst authorization and adjudication.
