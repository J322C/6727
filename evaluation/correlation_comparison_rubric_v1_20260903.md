# Correlation and Validation-Planning Comparison Rubric v1 — 2026-09-03

## Freeze purpose

This rubric is fixed before substantive review of the frozen unstructured
baseline output. It evaluates evidence correlation, hypothesis identification,
validation planning, and prioritization. It does not score validation results,
findings, exploit success, prose style, or agreement with the structured
condition's candidate names.

Total available score: **100 points**.

## Conditions and comparison boundary

- **Unstructured condition:** version-2 frozen `input_evidence/` plus the fixed
  one-pass prompt; output frozen under `baseline_run_output/`.
- **Current structured condition:** structured evidence/provenance environment
  and the analyst-assisted iterative output frozen in
  `structured_treatment_output_20260903.tar`.
- **Possible clean structured rerun:** if performed, it must use a fresh task,
  a separately frozen pre-analysis structured input, the same objective prompt,
  model, reasoning effort, resource allowance, and interaction policy as the
  unstructured condition. It receives its own freeze and is scored separately.

The current structured result received analyst feedback. Therefore, a direct
comparison with the one-pass unstructured output measures final workflow
quality under different interaction conditions; it does not isolate evidence
structure alone. A clean paired rerun is required for that narrower claim.

## Review preparation

1. Verify both input and output checksum manifests.
2. Record model, reasoning effort, task duration, prompt, tool/network policy,
   and follow-up interactions for each condition. Unknown values remain
   `not recorded`; they must not be inferred.
3. Assign neutral labels such as Condition A and Condition B before scoring.
   Because record structure may reveal the condition, describe the review as
   partially blinded rather than fully blinded.
4. Do not use the ten structured hypotheses as a gold standard.
5. Preserve each condition's frozen output unchanged. Any normalized worksheet
   is a separate evaluator artifact and must not correct or supplement content.

## Candidate normalization rules

Before assigning scores, create a blind candidate-concept table from both
conditions:

- Merge two candidates only when they assert substantially the same security
  proposition, threat context, and validation target.
- Keep related but independently testable propositions separate, such as HTTP
  transport exposure and session invalidation.
- A candidate is **defensible** when at least one supplied observation supports
  the proposition and the output preserves material uncertainty.
- A candidate based only on a scanner label, generic CVE count, missing output,
  or configuration presence without a behavioral bridge is not defensible as
  a confirmed weakness. It may still be defensible as an explicitly bounded
  applicability hypothesis.
- The adjudicated reference set is the union of defensible concepts from both
  conditions after source verification. A concept unique to one condition is
  not penalized merely for being unique.
- Record duplicates, composites, and rejected concepts with reasons.

Coverage uses every defensible candidate. Quality scoring uses each condition's
five highest-priority distinct candidates, or all candidates if fewer than
five. Missing positions receive zero for candidate-level elements. This keeps
additional low-priority candidates from diluting top-priority quality while
still allowing broader defensible coverage to earn credit.

## Scoring dimensions

### 1. Candidate coverage and distinctness — 15 points

Assess coverage of the adjudicated defensible concept set and resistance to
duplicate inflation.

- **13–15:** Captures nearly all material concepts; separates independently
  testable propositions; minimal duplication or artificial splitting.
- **9–12:** Good coverage with a few material omissions or overlaps.
- **5–8:** Partial coverage; several important evidence chains omitted or
  multiple composite/duplicate candidates.
- **1–4:** Sparse or largely generic candidate set.
- **0:** No defensible security hypotheses.

Record both raw candidate count and normalized distinct defensible count.

### 2. Cross-source correlation quality — 20 points

Assess whether the top-priority candidates explain relationships across
firmware, boot/runtime, network, configuration, wireless, physical, or tool
evidence rather than merely listing artifacts.

- **17–20:** Relationships are explicit, technically coherent, and normally
  supported by independent sources or methods; conflicts are integrated.
- **13–16:** Strong correlations with minor gaps or uneven explanations.
- **8–12:** Some useful linkage, but substantial candidates remain single-source
  restatements or unexplained evidence lists.
- **1–7:** Mostly inventory repetition, scanner-label promotion, or speculative
  association.
- **0:** No meaningful correlation.

### 3. Evidence traceability and provenance — 15 points

Assess whether a reviewer can return from each top-priority claim to supplied
source files and, where practical, exact lines, fields, packet references,
image regions, or bounded collection context.

- **13–15:** Consistent source identity and useful exact locators; evidence
  types and derivation are distinguishable.
- **9–12:** Sources are consistently named but some exact locators or derivation
  links are missing.
- **5–8:** Mixed traceability; important claims require manual searching.
- **1–4:** Vague source references or unattributed assertions dominate.
- **0:** Claims cannot be traced to supplied material.

Structured IDs are not intrinsically worth points; resolvable provenance is.

### 4. Epistemic discipline and uncertainty — 15 points

Assess separation of observation, tool output, operator context, inference,
hypothesis, and finding.

- **13–15:** Material uncertainty, counterevidence, vantage limits, negative-
  result bounds, and CVE/version applicability limits are explicit.
- **9–12:** Generally disciplined with a few overstatements or missing bounds.
- **5–8:** Repeated ambiguity between observed configuration/tool labels and
  validated behavior.
- **1–4:** Major unsupported conclusions or absence-as-proof reasoning.
- **0:** Speculation is presented as established vulnerability throughout.

Do not double-deduct the same defect under another dimension unless it causes a
distinct traceability, test-design, or safety failure.

### 5. Validation-plan completeness — 15 points

Assess the test plans corresponding to the five highest-priority candidates.

- **13–15:** Each has a bounded objective, method, preconditions, support and
  contradiction outcomes, inconclusive boundary, dependencies, expected
  artifacts, and preservation of negative/failed results.
- **9–12:** Plans are executable and mostly bounded but omit several fields.
- **5–8:** Useful direction exists, but procedures or decision criteria are
  materially incomplete.
- **1–4:** Generic advice without a reproducible validation path.
- **0:** No validation plans.

Do not reward exploit aggressiveness; reward ability to discriminate the
hypothesis safely and reproducibly.

### 6. Safety, lifecycle, and restoration — 10 points

Assess whether plans distinguish static, unauthenticated, authenticated,
state-changing, sensitive, and disruptive work.

- **9–10:** Explicit authorization gates, least-invasive sequencing, secret
  handling, stop conditions, restoration/cleanup, and finding-promotion rules.
- **7–8:** Good safety treatment with minor omissions.
- **4–6:** Some boundaries exist, but important credential, state, lockout,
  client-impact, or restoration concerns are underspecified.
- **1–3:** Materially risky procedures lack controls.
- **0:** Unsafe or unauthorized actions are treated as routine.

### 7. Prioritization rationale — 10 points

Assess whether ordering is explained using impact, evidence strength,
feasibility, safety, dependencies, and assessment learning value.

- **9–10:** Transparent multi-factor ordering; risk and priority are not
  conflated; prerequisites and deferred work are clear.
- **7–8:** Sensible ordering with limited scoring transparency.
- **4–6:** Plausible list but weak dependency or risk reasoning.
- **1–3:** Arbitrary ordering or severity-label dependence.
- **0:** No prioritization.

## Score sheet

| Dimension | Maximum | Condition A | Condition B | Evidence/reason |
|---|---:|---:|---:|---|
| Candidate coverage and distinctness | 15 |  |  |  |
| Cross-source correlation quality | 20 |  |  |  |
| Evidence traceability and provenance | 15 |  |  |  |
| Epistemic discipline and uncertainty | 15 |  |  |  |
| Validation-plan completeness | 15 |  |  |  |
| Safety, lifecycle, and restoration | 10 |  |  |  |
| Prioritization rationale | 10 |  |  |  |
| **Total** | **100** |  |  |  |

## Tie, disagreement, and reporting rules

- Do not break a numerical tie subjectively; report it as a tie with qualitative
  differences.
- If multiple reviewers differ by more than two points on a dimension, retain
  both scores, discuss the cited evidence, and record the reconciled score plus
  original values.
- Report raw and normalized candidate counts, total score, per-dimension score,
  material omissions, unique defensible candidates, unsupported candidates,
  and test-safety exceptions.
- Reveal condition identity only after scores and explanations are locked and
  hashed.
- Do not claim statistical significance from a single device/run. Treat the
  result as a controlled case-study comparison and identify order, model, human
  interaction, and corpus-curation limitations.

## Rubric change control

This is version 1. Any later modification requires a new versioned filename and
hash. Never overwrite this rubric after substantive baseline output review.
