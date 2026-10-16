# Archer C9 Evidence and Evaluation Reference Records

This repository is a deliberately limited publication bundle for the CS 6727 practicum, *Evidence-Grounded AI-Assisted Correlation for Embedded and IoT Security Assessments*. It contains the project records cited in the accompanying report and excludes the working repository, firmware images, raw captures, generated analysis outputs, condition keys, restricted evidence, credentials, session values, and device-control material.

## Scope

The published material supports review of the project's evidence/provenance model, paired-evaluation protocol, frozen review boundary, reported first-cohort results, security requirements context, and final hypothesis dispositions. It is not a reproduction package for live-device testing and does not authorize interaction with a device.

## Citation map

| Report reference | Published record or records |
|---|---|
| [8] Archer C9 2016 assessment evidence records | `evidence-records/E-0021.json`, `E-0023.json`, `E-0035.json`, `E-0062.json`, `E-0063.json`, and `E-0070.json` |
| [9] Clean Paired Correlation Comparison Protocol v1 | `evaluation/clean_paired_correlation_comparison_protocol_v1_20260904.md` |
| [10] Clean Paired-Rerun Freeze Record | `evaluation/clean_paired_rerun_freeze_record_20260904.md` |
| [11] Blind Scoring Protocol v1 and Correlation Comparison Rubric v1 | `evaluation/blind_scoring_protocol_v1_20260904.md` and `evaluation/correlation_comparison_rubric_v1_20260903.md` |
| [12] Revealed Paired Evaluation Results | `evaluation/revealed_paired_evaluation_results_20260906.md` |
| [13] F-0002 Evidence-to-Risk Demonstration | `assessment/f0002_evidence_to_risk_demonstration_20260910.md` and `figures/f0002_evidence_to_risk_chain_20260910.png` |
| [14] Security Requirements v2 | `requirements/Security_Requirements_v2.csv` |
| [15] Final Hypothesis, Test, Finding, and Risk Disposition Map | `assessment/final_hypothesis_disposition_map_20260924.md` |

## Interpretation boundary

The paired results describe one Archer C9 evidence corpus, five stochastic matched pairs, one generator configuration, one reviewer configuration, and partially blinded review. They do not establish statistical significance, a cross-device result, general model superiority, or an isolated effect of any individual structured field. The later requirements matrix served as common analytical context for the second cohort; it is not evidence of a causal matrix effect.

The evidence records preserve observations and locators. They do not independently establish exploitability or a security finding. The F-0002 demonstration shows why the project keeps evidence, hypothesis, authorized test, returned evidence, finding, and deployment-sensitive risk as separate records and decisions.

## Integrity checking

`SHA256SUMS` contains a SHA-256 digest for each published source record. Verify after cloning with:

```sh
sha256sum -c SHA256SUMS
```

## Publication safety

This bundle intentionally excludes sensitive raw material. The F-0002 narrative refers to value-suppressed, secret-safe derivative evidence only. It does not contain authentication values, response bodies, raw packet captures, passwords, condition keys, or operator credentials.

## Suggested citation

T. Carlisle, *Archer C9 Evidence and Evaluation Reference Records*, CS 6727 practicum publication bundle, 2026. Repository version and commit identifier should be included when available.
