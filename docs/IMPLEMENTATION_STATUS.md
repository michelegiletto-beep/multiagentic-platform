# Implementation status

**Terminal:** 1.1.25-rc.49 · **SCALPING LAB:** 2.2.6 · **Review date:** 19 October 2026

The review examined installed package metadata, selected implementation files and existing training, internal verification and passive operational records. The terminal and SCALPING LAB are separate packages with separate versions. The review did not launch them, repeat training or issue broker requests. This public repository distributes documentation and authorised images, excluding executables, implementation source, weights, private operational records and credentials.

## Implementation and recorded evidence

| Component | Implementation observed | Evidence limit |
| --- | --- | --- |
| Native platform | Agent lifecycle, scoped account context, market observations, analytical services and execution consumers | Behaviour was inspected in code, not exercised by this audit. |
| Terminal Scalping workspace | Instrument selection, quote freshness and readiness, positions, orders, recent activity, historical charts and compact monitoring | This operational workspace is distinct from SCALPING LAB. |
| SCALPING LAB 2.2.6 | Offline data-quality, campaign, replay, static-versus-adaptive comparison, stress and simulated-results workflow | Recorded campaigns include inconclusive and non-baseline-beating results; research promotion does not imply production deployment. |
| SPINS — Special Instructions | Model artifacts, engine wiring, readiness records and hash-linked training reports | Documented local CPU fits concern synthetic user-policy imitation. Final gates and real-market validation remain separate. |
| Learned profile selection | Scoped artifact validation, fixture rejection, setup-bound profiles and deterministic defaults | Model quality, deployment behaviour and comparative benefit remain to be evaluated. |
| Offline training | Dataset export, temporal splits, model comparison and artifact-integrity code; documented PyTorch CPU runs | No verified GPU campaign is linked to the shipped models in the reviewed evidence. |
| Optional LLM integration | Local scoped explanations, remote structured proposals and native contract compilation | The inspected release explicitly selects `NATIVE_ONLY` and disables both LLM paths. |
| LLM fallback controls | Queue bounds, deadlines, cancellation, capacity deferral, backend checks and fallback results | No measured saturation, failover latency or end-to-end continuity result is supplied. |
| Capital.com | Implemented account, market-data and execution-lifecycle adapter; documented live observations | Latest recorded passive audit, 16 October 2026: stale quotes despite connected status, diagnostic timeouts and degraded backend. Feed continuity unresolved. |
| IG and OANDA | Implemented provider adapters and internal mock tests | Full live qualification and provider approval are not established. |
| Internal software verification | Software checks and targeted benchmark records | Internal verification is distinct from continuous feed freshness and live operational qualification. |
| Audit and recovery | Scoped events, decision journals, application receipts and recovery components | Completeness and correctness across failure and restart require runtime evaluation. |

## Model readiness and scientific interpretation

Training reports document executed SPINS fits on synthetic policies, and model hashes link shipped artifacts to those records. The documented runs use local PyTorch CPU execution. The aggregate readiness manifest retains final gates; the review did not rerun training or establish real-market validation. Agreement with a specified policy does not measure prediction of market outcomes or financial performance.

No GPU training claim is made for the shipped models or a wider programme on the basis of the reviewed records. A different training campaign would require its own verifiable provenance and artifact linkage.

## Operational limits

The latest recorded Capital.com passive audit documents live observations alongside stale quotes, diagnostic timeouts and degraded backend conditions. A connected flag did not establish quote freshness. The reviewed evidence does not establish a verified fix or full feed-continuity qualification. These findings concern that recorded audit; subsequent operational improvement requires a new measurement record.

Internal software checks, mock provider tests and targeted benchmarks support specific implementation claims. They do not establish live-provider qualification or profitable trading. SCALPING LAB also retains inconclusive and non-baseline-beating campaign outcomes, which remain part of the research record.

## Native operation and optional supervision

The inspected release is configured for native operation. Optional LLM code remains present, but its activation is explicitly suppressed in this release. Public claims about enabled LLM behaviour must identify the relevant tested build and configuration. Implemented native defaults and fallback guards support a concrete validation programme; their existence does not establish uninterrupted autonomy under arbitrary failures.

VESPER remains a separate inference research design. Its RFC does not establish a working full-model runtime, a measured speedup or a completed platform integration.

[Architecture](ARCHITECTURE.md) explains the component boundaries. [SCALPING LAB](SCALPING_LAB.md) describes the separate offline research workflow. [Validation](VALIDATION.md) defines the tests required to qualify measured operational behaviour.
