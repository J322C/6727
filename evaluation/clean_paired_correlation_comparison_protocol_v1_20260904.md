# Clean Paired Correlation Comparison Protocol v1 — 2026-09-04

## Question

For the same collected Archer C9 observations, does an explicit evidence and
provenance structure improve AI-assisted correlation, hypothesis formation,
validation planning, prioritization, and reviewer traceability compared with
an unstructured file corpus?

## Fixed conditions

- Condition A receives the frozen 132-file post-collection source corpus.
- Condition B receives byte-identical copies of those 132 files plus a
  deterministic pre-analysis projection of the assessment, evidence, artifact,
  and applicable schema records. The evaluator-side projection rules remove
  only explicit correlation/validation-direction tags left by the earlier
  analyst-assisted workflow.
- Neither condition receives prior correlation products, hypotheses, planned
  tests, findings, risk rationales, project summaries, analyst notes, proposal
  text, progress reports, or prior run outputs.
- The added records are the treatment: they organize observations and
  provenance. They must not include candidate hypotheses or test decisions.

The labels-to-condition mapping is retained only in the evaluator-side
`condition_key_v1_20260904.md`; it is not copied into runner or blind-scoring
workspaces. Record structure can still reveal the treatment, so review is
described as partially blinded.

## Matched execution controls

- Five paired replicates are provisioned: R01 through R05.
- Use model `gpt-5.6-sol` with reasoning effort `high` for every run.
- Use a fresh Codex task for every run; do not fork a project-development task.
- Send only: `Follow AGENTS.md and complete protocol/common_prompt.md.`
- No follow-up messages, candidate hints, web access, subagents, or live DUT
  access are permitted.
- Each run gets its own byte-isolated input copy and empty output directory.
- Alternate order to reduce order effects: R01 A→B, R02 B→A, R03 A→B,
  R04 B→A, R05 A→B.
- Complete the metadata record and freeze output hashes immediately after each
  run. A deviation does not get silently corrected; record it and decide later
  whether the run is excluded or repeated under a new run ID.

## Output and freeze controls

Each run must produce only the five files named in the common prompt. Preserve
them verbatim. Create a relative-path SHA-256 manifest and record the manifest's
own SHA-256. Normalization, scoring notes, or corrections are separate evaluator
artifacts and may not change a run output.

## Scoring gate

Do not score until the complete paired output set selected for analysis is
frozen. Use `correlation_comparison_rubric_v1_20260903.md` unchanged. Build the
blind candidate-concept table before revealing condition identity. Preserve
individual scores, reconciliation, exclusions, and the locked score package.

## Dynamic-testing boundary

This comparison begins after evidence collection and ends before validation
execution. Dynamic results may be evaluated later only as a separately
versioned, parity-controlled post-test corpus. The clean rerun does not replace
the existing analyst-assisted structured snapshot or the first unstructured
pilot output; those remain historical workflow/pilot artifacts.
