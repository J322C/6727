# Revealed Paired Evaluation Results — 2026-09-06

## Scope

This report reveals and aggregates the already locked blind scores for five
paired clean runs. In every pair, the generator model, reasoning setting, task
prompt, underlying source evidence, and required deliverables were held
constant. The evaluated intervention is access to the structured
evidence/provenance projection in addition to the common source corpus.

These are descriptive controlled-case-study results for one device corpus, one
generator model/configuration, and one blind reviewer. They do not establish a
population-level or statistically significant effect.

## Primary result

| Measure | Unstructured | Structured | Difference |
|---|---:|---:|---:|
| Mean rubric score | 93.4 | 95.2 | +1.8 structured |
| Median rubric score | 94 | 95 | +1 structured |
| Score range | 92–95 | 92–97 | — |
| Sample standard deviation | 1.34 | 2.05 | — |
| Mean raw candidate count | 6.8 | 7.6 | +0.8 structured |
| Mean normalized defensible count | 6.8 | 7.4 | +0.6 structured |

The paired score differences (structured minus unstructured) were `+3, -2, 0,
+3, +5`, giving a mean of `+1.8`, median of `+3`, and sample standard deviation
of `2.77`. Three pairs favored the structured condition, one tied, and one
favored the unstructured condition. The descriptive paired standardized mean
difference is approximately `0.65`, but with only five non-independent case
replicates it is not used as a significance claim.

The result is therefore a modest, variable advantage for the structured
condition—not a sweep and not evidence that structure alone guarantees a
better analytical output.

## Where the score difference came from

| Rubric dimension | Unstructured mean | Structured mean | Difference |
|---|---:|---:|---:|
| Candidate coverage and distinctness /15 | 13.0 | 13.4 | +0.4 |
| Cross-source correlation quality /20 | 18.2 | 18.2 | 0.0 |
| Evidence traceability and provenance /15 | 14.6 | 15.0 | +0.4 |
| Epistemic discipline and uncertainty /15 | 12.8 | 13.6 | +0.8 |
| Validation-plan completeness /15 | 14.8 | 15.0 | +0.2 |
| Safety, lifecycle, and restoration /10 | 10.0 | 10.0 | 0.0 |
| Prioritization rationale /10 | 10.0 | 10.0 | 0.0 |

Epistemic discipline contributed the largest mean difference, but it was also
the least stable paired dimension: its five differences were `-1, -4, -1, +4,
+6`. In R02, the structured output asserted an authenticated Basic/content
transmission that the supplied evidence did not capture. Structure improved
the average here, but did not prevent overstatement.

Correlation quality was identical on average. Validation plans, safety, and
prioritization were already near or at the rubric ceiling in both conditions,
leaving little room for differentiation.

## Candidate retention and distinctness

All ten packages explicitly retained the four central concepts: cleartext HTTP
management, UPnP state-change exposure, WPS behavior, and legacy SSH
negotiation. NetUSB appeared explicitly in four of five outputs in each
condition.

The clearest structural difference was session lifecycle. It appeared as a
distinct candidate in all five structured outputs and zero of five
unstructured outputs. One unstructured output discussed it as context under
the HTTP concept, so `0/5` describes explicit candidate separation rather than
complete absence from the analysis.

Long-tail concept retention was mixed rather than uniformly better under the
structured condition:

| Concept | Unstructured | Structured |
|---|---:|---:|
| SSH throttling | 4/5 | 3/5 |
| Session lifecycle | 0/5 | 5/5 |
| PMF/deauthentication | 2/5 | 1/5 |
| UART/root verifier applicability | 3/5 | 2/5 |
| Configuration-backup applicability | 1/5 | 2/5 |

This supports a narrow inference: the structured projection consistently
helped preserve one cross-domain lifecycle proposition as a separate unit. It
does not support claiming that structured input captured every peripheral
concept more reliably.

## Operational traceability

Each condition had 50 reference-resolution attempts: 49 successes, one
partial result, no failures, and no timeouts. Successful attempts in both
conditions had a median of one file opened and one local search operation.

Because the reviewer did not record active elapsed seconds for any attempt,
the evaluation cannot determine whether structured input reduced traceability
time or analyst effort. The rubric gave the structured condition a small
traceability-quality advantage (`+0.4` mean), but observed resolution success
and median operation counts were identical.

## Reviewer-identified overstatements

The reviewer rejected one structured candidate that inferred inadequate
firmware authenticity from the absence of boot text. Other material epistemic
deductions involved an unstructured output that overclaimed HTTP and UPnP
behavior, a structured output that overclaimed authenticated HTTP transmission,
and an unstructured output that overclaimed NetUSB parser exposure, UART
verifier recoverability, and configuration-backup contents.

No package had a safety exception. The review also did not convert any
hypothesis into a finding: decisive dynamic facts remain untested.

## Interpretation and limitations

The frozen comparison supports the defensible conclusion that, in this Archer
C9 case, adding the structured evidence/provenance layer produced a small
average improvement and a strong consistency benefit for isolating the session
lifecycle hypothesis. The underlying analytical quality remained high in both
conditions.

Important limits are:

- only five paired stochastic runs were evaluated;
- all runs used one generator model/configuration and one fixed prompt;
- one reviewer scored all outputs, so inter-rater reliability is unknown;
- the reviewer was identity-blind but could potentially infer presentation
  style or structure from the outputs and references;
- repeated runs share the same device evidence and are not independent device
  samples;
- rubric ceiling effects reduce separation in planning, safety, and priority;
- no usable time-on-task measurements were collected; and
- the intervention includes a curated structured evidence/provenance
  projection, so the result should not be attributed to schema format alone.

## Recommended next evaluation step

Before using these results in a report, perform a bounded human audit of the
ten scorecards and the concept mapping for transcription or interpretation
errors. If schedule permits, a second independent blind reviewer would be the
most valuable extension because it tests whether the modest score advantage
survives reviewer variation. Neither step requires repeating evidence
collection or restarting the technical assessment.

After that review gate, the project can move to separately authorized,
hypothesis-directed dynamic validation. The present evaluation does not itself
authorize any test or establish any finding or risk rating.

