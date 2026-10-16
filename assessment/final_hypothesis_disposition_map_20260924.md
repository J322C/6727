# Final Hypothesis, Test, Finding, and Risk Disposition Map

**Assessment:** A-C9-2016  
**Date:** September 24, 2026  
**Campaign state:** Active technical testing closed; remaining candidates are
optional future work

## Purpose

This map is the reporting bridge from correlation through validation and
adjudication. It distinguishes four outcomes that must not be collapsed:

1. a hypothesis can be supported by a bounded test;
2. a hypothesis can be contradicted within the tested boundary;
3. a supported hypothesis can remain an observation rather than a finding; and
4. an unvalidated hypothesis can remain legitimate future work.

## Portfolio summary

| Record class | Final count or state |
|---|---:|
| Formal hypotheses | 10 |
| Supported hypotheses | 7 |
| Boundedly contradicted hypotheses | 1 |
| Unvalidated hypotheses | 2 |
| Formal validation tests | 15 |
| Completed tests | 11 |
| Deferred future-work tests | 4 |
| Accepted findings | 3 |
| Accepted risk rationales | 3 |

The optional FV-UPNP-01 branch is not a formal numbered test and remains future
work.

## Final disposition map

| Hypothesis | Completed or deferred tests | Final state | Finding/risk outcome | Reporting interpretation |
|---|---|---|---|---|
| H-0001 — guest isolation may be incomplete | T-0001 completed; E-0112, E-0113 | **Contradicted within the bounded matrix** | No finding | The selected 2.4 GHz guest client reached the gateway but not the selected LAN host/service or an accepting HTTP, HTTPS, or SSH management service. This is useful negative evidence, not universal proof of isolation. |
| H-0002 — recoverable embedded credential may enable UART root access | T-0002 and T-0003 completed; E-0101, E-0105, E-0106 | **Supported** | F-0001; R-0001 | The candidate was recovered within the bounded offline audit and accepted by the physical DUT. Impact is high after access; likelihood is moderated by PCB/UART physical-access prerequisites. |
| H-0003 — cleartext web management exposes authentication material/content | T-0004 completed; E-0102 | **Supported** | F-0002; R-0002 | Repeated authentication material and readable administrative content crossed cleartext HTTP. This is the highest remediation priority among the three findings for the tested deployment context. |
| H-0004 — SSH permits legacy pre-authentication negotiation | T-0005 completed; E-0103 | **Supported** | F-0003; R-0003 | Four selected deprecated algorithm classes negotiated before credentials. This is a low-to-moderate hardening risk, not evidence of authentication bypass or code execution. |
| H-0005 — unauthenticated read-only UPnP actions expose operational state | T-0006 completed; E-0104 | **Supported** | No finding | The behavior was demonstrated, including a correct `0.0.0.0` external address in the no-WAN state, but no sensitive disclosure, state change, external trust-boundary crossing, or exploitability was shown. |
| H-0006 — logout in one browser may not invalidate another context | T-0007 completed; E-0107 | **Supported and mechanism narrowed** | No separate finding | A second browser retained its Basic-prefixed authentication state and continued receiving live responses after logout in the first. The evidence does not demonstrate a conventional server-generated session identifier or cross-host credential replay; it extends the management-plane narrative without forcing a new finding. |
| H-0007 — TCP/33344 is the runtime KCodes NetUSB implementation | T-0008 and T-0015 completed; T-0009 deferred; E-0098–E-0100, E-0111 | **Supported within convergent-attribution boundary** | No finding | Static identity, startup, listener, module, and kernel-thread evidence converge on NetUSB. Direct inode-to-module-symbol proof and exploitability were not established, so runtime identity remains evidence rather than a vulnerability finding. |
| H-0008 — WPS PIN provides an alternate authorization/credential path | T-0010 and T-0011 deferred | **Unvalidated; future work** | No finding | UI, passive radio, and operator context make the question plausible, but no WPS transaction occurred. PIN acceptance, credential equivalence, throttling, and lockout remain untested. |
| H-0009 — update/boot paths lack a vendor signer-authenticity decision | T-0012 and T-0013 completed; E-0108–E-0110 | **Supported within traced-path boundary** | No finding | The located web-to-write and CFE-to-boot paths use length, fixed-constant MD5, structure/compatibility, HDR0, and CRC32 checks without a located public-key signer decision. No modified image was submitted, so acceptance, execution, persistence, or remote exploitability was not demonstrated. |
| H-0010 — lack of PMF may permit targeted client deauthentication | T-0014 deferred | **Unvalidated; future work** | No finding | Passive RSN capability evidence makes the behavior plausible, but the deliberately disruptive client test was not executed. |

## Finding and risk ordering

| Priority | Finding | Demonstrated boundary | Contextual conclusion |
|---:|---|---|---|
| 1 | F-0002 / R-0002 — cleartext management | Trusted-LAN management path | Highest remediation priority because an on-path observer does not need router credentials to observe a legitimate management exchange |
| 2 | F-0001 / R-0001 — UART root credential path | Physical PCB/UART boundary | High demonstrated impact, moderate contextual likelihood because physical access and serial interaction are prerequisites |
| 3 | F-0003 / R-0003 — legacy SSH negotiation | Trusted-LAN SSH transport | Low-to-moderate hardening risk; exposure opportunity is elevated because SSH was reachable in the operator-reported factory-default state |

This ordering is contextual rather than a universal numerical severity scale.

## What changed because of validation

- H-0001 moved from a plausible cross-domain concern to bounded contradiction.
- H-0002 through H-0004 moved from hypotheses to three narrowly worded
  findings with accepted risk rationales.
- H-0005 produced a positive functional result but stopped below the finding
  threshold.
- H-0006 retained the session-lifecycle concern while narrowing its mechanism
  to browser-local retained authentication state in the tested sequence.
- H-0007 moved from static/service-label correlation to strong convergent
  runtime attribution without becoming an exploitability claim.
- H-0009 moved from absence-oriented suspicion to positive control-flow tracing
  of two located acceptance paths, while retaining a no-modified-image boundary.
- H-0008 and H-0010 remain explicitly unresolved rather than being silently
  treated as false.

## Reporting boundary

The disposition map belongs to the post-evaluation assessment loop. It can show
that structured records supported downstream validation, correction, and claim
narrowing. It must not be used to retroactively rescore the five frozen paired
runs or imply that the generators had access to later test results.

