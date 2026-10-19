# Multiagentic Platform

**Multiagent trading research and portfolio allocation**

[Available releases](#download) · [Hugging Face Space](https://huggingface.co/spaces/Magic51/multiagentic-platform) · [Platform dossier](docs/ARCHITECTURE.md) · [SPINS](docs/SPINS.md) · [Scalping Lab](docs/SCALPING_LAB.md) · [VESPER](docs/VESPER.md) · [Support development](#support)

Multiagentic Platform is the flagship trading research and portfolio allocation programme developed by Michele Giletto at System Labs. It develops the Reasoning Agent into a coordinated environment for market analysis, statistical learning and bounded decision workflows. In its first equity-portfolio application, agents work with market observations, positions, exposure and proposed allocation decisions within a common operating context.

The installed implementation combines native analytical services, SPINS model components, broker adapters and explicit execution controls. Optional LLM integration code is present; the inspected build selects `NATIVE_ONLY` and disables those paths. Shipped SPINS artifacts are linked to documented local CPU training runs. VESPER is a complementary research track for inference under memory and I/O constraints.

**Public release version: 1.1.25.** The Windows installer is being prepared for publication through GitHub Releases. Availability of the executable is recorded in [Download](#download).

Installed build **1.1.25-rc.49** was inspected statically on **19 October 2026**, alongside training, software-verification and passive operational records. That identifier is retained to identify the historical evidence reviewed; the public installer has been assigned version **1.1.25** and requires its own package checks. The review did not launch the program, call brokers or place trades. Public release status does not establish additional operational qualification. Implementation source, model weights, training data and credentials remain proprietary and excluded from this repository.

## Download

[View available releases](https://github.com/michelegiletto-beep/multiagentic-platform/releases)

No Windows installer is currently attached to a public release. GitHub's **Download ZIP** downloads this documentation repository, not the application. The **1.1.25** installer, installation instructions, licence terms and SHA-256 checksum will be added to the release record after the package has been checked and uploaded. Checks of that installer will be reported separately from the historical build inspection below.

## Interface

![Multiagentic Platform trading research interface with an instrument list, candlestick workspace and agent companion](assets/trading-terminal.jpg)

Developer-supplied interface screenshot showing an instrument list, a candlestick workspace and an agent companion. Displayed prices and chart levels are screen content, not live data or measured strategy performance. Broker integration status is described in the evidence table below.

The terminal's Scalping workspace presents instruments, quote freshness, positions, orders and recent activity. **SCALPING LAB 2.2.6** is a separate offline research package for historical-data quality, campaigns, static-versus-adaptive comparisons, replay and simulated results. Its [research workflow](docs/SCALPING_LAB.md) is distinct from the terminal's operational workspace.

## Technical scope

The inspected implementation separates these responsibilities:

| Component | Responsibility |
| --- | --- |
| Statistical and neural components | Load versioned analytical and SPINS model artifacts; final activation and validation gates remain explicit. |
| Specialist agents | Perform bounded market analysis and portfolio research tasks, exchanging structured results. |
| Optional LLM supervision | Produce scoped explanations or structured proposals; disabled in the inspected native-only build. |
| Deterministic control layer | Apply permissions, portfolio exposure limits, admission rules and execution checks. |
| Broker adapters | Translate authorised execution requests into provider-specific order and account semantics. |
| Audit and recovery services | Preserve trading decision context, reconcile portfolio and execution state, and support controlled recovery. |

The engineering difficulty lies in the interaction of temporal learning, changing portfolio state, heterogeneous agents, inference costs and execution reliability. A model that fits historical data does not by itself establish a useful allocation policy. A coherent agent plan does not establish that an action is permitted, executable or correctly recorded. Evaluation must measure those interfaces as well as each component.

## Evidence and development status

| Statement | Evidence category | Current interpretation |
| --- | --- | --- |
| Inspected build 1.1.25-rc.49 and native agent workflow | Source-inspected implementation | Historical installed package and implementation examined; no execution test in this audit. |
| SPINS — Special Instructions | Inspected artifacts and documented CPU training | Shipped model artifacts match training records; final gates remain. Synthetic policy imitation does not establish profit prediction. |
| SCALPING LAB 2.2.6 | Separate offline research implementation and campaign records | Includes inconclusive and non-baseline-beating results; no production promotion implied. |
| Optional LLM supervision and fallback controls | Source-inspected implementation | Code exists; LLM paths disabled by `NATIVE_ONLY`. Saturated failover remains unmeasured. |
| Capital.com | Inspected adapter and documented live observations | Latest recorded passive audit, 16 October 2026: feed continuity unresolved, with stale quotes and degraded diagnostics. |
| IG and OANDA | Inspected adapters and internal mock tests | Full live qualification and provider approval are not established. |
| VESPER resource-constrained inference | Published research design, RFC 0001 | No working full-model runtime or measured speedup established by that RFC. |

No parameter count, model depth, training scale, predictive accuracy, execution latency or investment return is claimed without a corresponding measurement record.

## Public architecture and evaluation

[Implementation status](docs/IMPLEMENTATION_STATUS.md) records the inspected builds and limits. [Architecture](docs/ARCHITECTURE.md) explains component boundaries. [Validation](docs/VALIDATION.md) defines the evaluation protocol. [SCALPING LAB](docs/SCALPING_LAB.md) covers offline experiments; [VESPER](docs/VESPER.md) covers inference research.

The public record includes the [platform overview](https://giletto-systems-lab.michele-giletto.chatgpt.site/reasoning-agent.html), [VESPER project](https://giletto-systems-lab.michele-giletto.chatgpt.site/projects/vesper.html) and [VESPER RFC 0001](https://giletto-systems-lab.michele-giletto.chatgpt.site/materials/VESPER_RFC_0001.md). These sources document the programme and its stated development status; they do not substitute for implementation inspection or independent testing.

## Support

[Contribute through PayPal](https://www.paypal.com/qrcodes/p2pqrc/UG8AQFP5LPVU2) to support independent development.

<a href="https://www.paypal.com/qrcodes/p2pqrc/UG8AQFP5LPVU2"><img src="assets/paypal-qr.jpg" alt="PayPal contribution QR code supplied by Michele Giletto" width="180"></a>

Contributions are voluntary and do not grant a software licence, product access, intellectual property rights, investment participation, promised returns or a support commitment. Commercial rights and services require a separate agreement.

## Evaluation, licensing and strategic discussions

Companies and technical partners may request a scoped evaluation, commercial licensing discussion or strategic acquisition discussion. An evaluation can begin with a defined use case, available evidence, a test environment and agreed acceptance criteria. Proprietary implementation material can be considered separately under agreed confidentiality terms.

Contact [Michele Giletto](mailto:michele.giletto@gmail.com?subject=Multiagentic%20Platform%20evaluation%20and%20licensing) for evaluation, licensing or acquisition enquiries.

## Copyright

© 2026 Michele Giletto. All rights reserved. Multiagentic Platform is proprietary software. Public release and download availability do not grant rights to the implementation source or model weights. Use of a distributed installer is governed by the licence supplied with that release; this dossier grants no broad software licence. See [COPYRIGHT.md](COPYRIGHT.md). Citation metadata is provided in [CITATION.cff](CITATION.cff).
