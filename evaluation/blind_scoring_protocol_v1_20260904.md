# Blind Scoring Protocol v1 — 2026-09-04

## Purpose

Score ten frozen analysis packages without access to the evaluator's mapping of
package IDs to run, replicate, or condition. The review is partially blinded:
the analytical writing may reveal differences in source organization even
though labels and filesystem metadata are neutralized.

## Inputs

- Ten neutral directories under `review_packages/`, each containing the same
  five required analytical deliverables.
- The frozen 100-point comparison rubric under `rubric/`.
- A shared union reference corpus under `reference_material/`. It contains the
  common 132 source files and the non-directional structured records so that
  both file references and record identifiers can be resolved. Its presence
  does not identify which material any reviewed package originally received.
- The frozen traceability-resolution protocol and blank worksheets.

## Review sequence

1. Verify `package_manifest.sha256` before substantive review.
2. Record reviewer/model metadata and any deviation in
   `review_output/review_method_log.md`.
3. Read all ten packages once without scoring to identify candidate concepts.
4. Build one union concept dictionary in
   `review_output/candidate_concept_table.md`. Apply the rubric's merge,
   distinctness, defensibility, duplicate, composite, and rejection rules.
5. Map every package's candidates to the union dictionary. Do not rename or
   improve a package's proposition.
6. Score each package independently using the seven frozen rubric dimensions.
   Use its five highest-priority distinct candidates for candidate-level quality
   dimensions, as the rubric specifies. Write one scorecard per neutral package
   under `review_output/scorecards/`.
7. Complete the traceability attempts under the frozen add-on protocol. Record
   actual reviewer effort; do not invent elapsed times. If reliable active time
   is unavailable, enter `not recorded` and retain the other resolution fields.
8. Write `review_output/blind_summary.md` with package-level totals,
   per-dimension scores, raw and normalized candidate counts, material
   omissions, unique defensible concepts, unsupported concepts, and safety
   exceptions. Do not group packages into conditions or speculate about labels.
9. Run internal arithmetic and completeness checks, then create
   `review_output/review_output_manifest.sha256` covering every review output.
   Stop. The evaluator reveals identities and calculates condition aggregates
   only after this blind output is locked and independently copied.

## Required scorecard fields

Each package scorecard must include:

- neutral package ID;
- raw candidate count;
- normalized distinct defensible count;
- five candidates used for candidate-level scoring;
- all seven dimension scores and cited reasons;
- total out of 100;
- material omissions and rejected/unsupported concepts;
- validation-plan safety exceptions; and
- arithmetic check.

## Scoring discipline

- Use only claims present in the reviewed package. Shared reference material
  verifies a citation; it must not repair an omitted citation or add reasoning.
- Structured identifiers receive no intrinsic credit.
- Penalize unsupported certainty where the rubric directs, but do not double
  deduct one defect unless it causes a distinct failure in another dimension.
- Preserve ties. Do not force a ranking.
- This is a descriptive controlled case study with five replicates per
  condition; do not claim statistical significance.

