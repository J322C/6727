# Clean Paired-Rerun Freeze Record — 2026-09-04

## Purpose and boundary

This record freezes the clean paired comparison package created in response to
proposal feedback. The package restarts evaluation immediately after evidence
collection; it does not repeat collection and does not alter the existing
analyst-assisted structured snapshot or unstructured pilot output.

No DUT request, validation test, device modification, scoring, or substantive
review of the five frozen unstructured pilot outputs occurred during this
phase. The builder neither reads nor copies pilot output directories.

## Isolated destination

`/home/kali/c9_correlation_eval/`

The destination did not exist before the build. It is outside the Archer C9
assessment repository so fresh runner tasks do not inherit the project's
candidate history, progress-report context, or current-checkpoint instructions.

## Provisioned workspaces

Ten fresh workspaces exist: Conditions A and B for each of R01 through R05.
Every workspace has an identical runner `AGENTS.md`, common prompt, blank run
metadata template, empty output directory, and an independent input copy.

- Each Condition A input contains 132 source files.
- Each Condition B input contains the same 132 byte-identical source files,
  82 evidence records, 126 referenced artifact records, one assessment record,
  and three applicable JSON schemas: 344 files total.
- All 10 source copies verified 132/132 against the version-2 baseline manifest.
- All 10 run input manifests verified with zero failures.
- Input files have no write permission.
- The isolated package occupies approximately 317 MiB.

Replicate input-manifest identities are constant:

- Condition A: `5d41bb39b4d2d6a9713629ba24cef1ba47c85a97aabede5b23fdbcd2973729da`
- Condition B: `f6c7346ff6b97165b0f7a7a14dc9c4e58ed2aac85921015344dd4ca8fa58256f`

## Structured pre-analysis projection

Nine evidence records contained ten explicit correlation/validation-direction
tags left by the earlier analyst-assisted process. The deterministic projection
removed only the five tag values listed in
`structured_projection_rules_v1_20260904.md`. It did not modify observations,
structured data, uncertainty statements, source metadata, target context,
confidence, locators, artifact references, or other tags. The exact removal log
is retained evaluator-side.

Filename and content leakage checks found no formal H-/T- identifiers,
hypothesis/test directories, prior correlation products, candidate registers,
prioritization products, findings, risk rationales, analyst notes, reports, or
directional tags in the runner inputs.

## Frozen controls

- Common prompt SHA-256:
  `7c03b720b6e9bea4c9afdd474ef9dd5445dfceee2e0200a8cf3d2d0cd9f1c2da`
- Runner `AGENTS.md` SHA-256:
  `9ad445996eeaf95b640b32c5b32fd42e513f59b579b1d1c3851e4b01d95cd8cd`
- Comparison protocol SHA-256:
  `fc6e7f5c006b95169cce8ca25cd5052b6fc6632967bffab21278296a58e39ae7`
- Structured projection rules SHA-256:
  `bb6653ead97b9ee3469b61807ec168884705ebf3e9b238fb833fe313045518d1`
- Traceability add-on SHA-256:
  `b4243d6900e7242a22129d1a43ecb992878d7eaecc17fa909f5945616f0ca003`
- Frozen rubric SHA-256:
  `2c3938efd5fb3ecd07cfe50478470608afb5fb5ae2f3d7cc0d93c90531dfe2f1`
- External package freeze-manifest SHA-256:
  `3c859c5ef34afb17be3cdb931bd554a54fbe2275a0ab6180ec66454a83117be3`

The private condition key remains only in the evaluator-side project control
directory. It is not present in runner workspaces or the blind-scoring area.

## Next gate

Run R01 as the first matched pair using the fixed model and effort, beginning
with Condition A according to the alternating-order protocol. Use fresh Codex
tasks rooted at the individual run directories and send only the fixed launch
instruction. Freeze both outputs and metadata before inspecting conclusions or
starting R02. No dynamic validation begins during these runs.

