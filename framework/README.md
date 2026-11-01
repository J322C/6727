# Prototype Correlation Framework

This directory documents Deliverable 1 from the practicum proposal: a prototype correlation framework for embedded and Internet of Things security assessment. The prototype is a controlled workflow and record model. It does not operate as an autonomous vulnerability scanner or authorize device interaction.

## Purpose

The framework preserves a reviewable route from heterogeneous source artifacts to a bounded risk rationale. It keeps observations, hypotheses, tests, findings, and risk decisions as separate records so that a reviewer can inspect the evidence and the limits of a conclusion.

## Workflow

1. **Onboard the device and threat context.** Record the target identity, test scope, interfaces, assets, trust boundaries, attacker positions, and safety limits.
2. **Register source artifacts and observations.** Artifact records use stable `AR-` identifiers, source paths, SHA-256 hashes, and collection context. Evidence records use stable `E-` identifiers, source locators, and bounded observation language.
3. **Correlate evidence and form hypotheses.** AI-assisted analysis may propose cross-source relationships, hypotheses, and validation plans. The analyst reviews the output before it enters the formal assessment portfolio.
4. **Plan and authorize bounded tests.** A validation-test record specifies the objective, preconditions, procedure, expected support or contradiction criteria, safety limits, and restoration requirements. Planning approval does not authorize execution.
5. **Return validation evidence.** Positive, negative, partial, failed, and deviation outcomes return to the evidence record rather than silently replacing an earlier claim.
6. **Adjudicate findings and contextual risk.** A supported hypothesis becomes a finding only after analyst review of returned evidence. Risk rationale then records the relevant attacker position, affected boundary, demonstrated impact, and remaining exclusions.

## Public project evidence of the workflow

- [`../evidence-records/`](../evidence-records/) contains selected citation-safe evidence records with artifact IDs and exact source locators.
- [`../assessment/final_hypothesis_disposition_map_20260924.md`](../assessment/final_hypothesis_disposition_map_20260924.md) records the final status of hypotheses, tests, findings, and risk rationales.
- [`../assessment/f0002_evidence_to_risk_demonstration_20260910.md`](../assessment/f0002_evidence_to_risk_demonstration_20260910.md) demonstrates one bounded route from source observations through test evidence to F-0002/R-0002.
- [`../schema/`](../schema/) supplies the reusable record definitions that structure the framework.

## Analyst-control and claim boundary

The analyst controls scope, test authorization, device-facing execution, evidence handling, finding promotion, and final risk judgment. A model-generated correlation or a technically positive observation does not by itself establish exploitability, a finding, or risk.

The completed Archer C9 case retains several different outcomes: a bounded contradiction of a guest-isolation concern, a positive read-only UPnP observation that remained a non-finding, three narrowly written findings, and deferred future-work branches. This distinction is a design requirement of the framework rather than an absence of results.

## Public-release boundary

The full local assessment includes restricted source artifacts and raw validation material. This public bundle includes only value-suppressed records and documentation needed to review the framework. It excludes live credentials, authentication values, raw captures, proprietary firmware, condition mappings, and device-control material.
