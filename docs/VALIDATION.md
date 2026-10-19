# Validation protocol

This protocol specifies how Multiagentic Platform can be evaluated without publishing proprietary model recipes or trading logic. It is an evaluation plan. The tests and acceptance gates below are not presented as completed results.

## Evidence categories

Every externally stated claim should identify its scope and supporting record. The 19 October 2026 review considered historical terminal build 1.1.25-rc.49, separate SCALPING LAB package 2.2.6, selected implementation files and existing records. The review did not launch the programs, contact brokers or execute trades. Static inspection, internal test records, training provenance and operational observations are different evidence categories. The project's public release designation does not alter those records; a later installer must identify its own version and the checks actually completed for that package.

| Category | Evidence available in this dossier | Permitted conclusion |
| --- | --- | --- |
| Public source record | Platform description and VESPER RFC | The programme, research questions and stated status are documented. |
| Source-inspected implementation | Terminal, separate research lab, native workflows, SPINS artifacts, optional LLM code and broker adapters | Selected components and wiring exist in code. |
| Documented training | Local PyTorch CPU reports linked by artifact hashes to shipped SPINS models | Synthetic policy fits were executed; market-profit prediction and GPU training are not established. |
| Internal software verification | Selected software checks, targeted benchmarks and provider mock tests | Tests support their declared software scope; they do not qualify continuous live operation. |
| Recorded operational observations | Capital.com live observations and passive audit dated 16 October 2026 | The latest recorded audit reports unresolved feed continuity, stale quotes and degraded diagnostics. |
| Validation pending | SPINS final gates, enabled LLM operation, saturated fallback and live provider qualification | Deployment readiness and end-to-end operational reliability remain separate gates. |
| End-to-end qualification | No complete qualification record supplied | Internal checks and historical observations do not establish uninterrupted autonomy, predictive advantage or investment returns. |

A future result record should name the tested software and model versions, environment, workload, comparison conditions, exclusions, measurements and uncertainty. Independent review should distinguish source inspection, developer-run tests and reproduced results.

SCALPING LAB campaigns include inconclusive and non-baseline-beating outcomes. Static-versus-adaptive comparisons and simulated curves must retain those results. Candidate export or a promotion record is a research workflow event; production deployment requires a separate, explicit qualification.

## Temporal data and leakage control

Define the decision time and the information genuinely available at that time. Preserve publication delays, revisions, market calendars and the timing of corporate actions. A historical value stored in a modern database may differ from the value available to an earlier decision.

Partition training, model selection and final evaluation in chronological order. Fit transforms, feature selection, imputation and calibration using only the permitted training history. Where labels or samples overlap across windows, define an exclusion or embargo policy appropriate to that overlap before final evaluation.

Use a point-in-time instrument universe when a universe is part of the experiment. Document survivorship, delistings, missing observations and unavailable instruments. Keep final evaluation periods separate from model selection. Repeated inspection of a held-out period should be recorded as an additional selection decision.

Use rolling or expanding temporal evaluation when it matches the intended deployment. Report each evaluation window and variation across market conditions. A single favourable interval is insufficient to establish stability.

## Numerical models and decision quality

Specify the task and intended use before choosing metrics. Policy imitation, pattern classification, price prediction and portfolio allocation require different evaluations. The inspected SPINS artifacts identify synthetic user-policy imitation as their training domain. Agreement with generated policy labels does not measure profit probability or market predictive advantage.

For a prediction study, define the target and horizon, then evaluate numerical error, calibration and ranking or classification quality where relevant. Compare against simple persistence, statistical and other suitable baselines using the same data availability rules. For policy imitation, evaluate agreement, held-out policy cases and divergence from the intended rules separately from any market-outcome study.

Distinguish prediction quality from allocation quality. An allocation study requires its own reference policy, exposure constraints and execution assumptions. If transaction costs, slippage, market impact, financing or product-specific charges are relevant, include and stress them explicitly. Avoid interpreting a frictionless historical simulation as evidence of attainable execution results.

Report uncertainty, failed cases and sensitivity to reasonable assumptions. Document all material model selection and repeated testing. This repository makes no profitability, expected return or financial suitability claim.

## Orchestration baselines and ablations

Use the inspected native workflow as an explicit reference. The rc.49 package disables its optional LLM paths through `NATIVE_ONLY`; evaluating enabled LLM operation therefore requires a separately identified and qualified build or configuration. Compare that condition with a fixed workflow, a deterministic rule-based scheduler and an appropriate non-LLM method. Keep inputs, numerical services, permissions and resource budgets comparable.

Useful ablations include removing LLM replanning, removing a specialist agent, replacing a numerical component with its baseline and disabling a resource-management optimisation. Each ablation should answer a stated question about the contribution of that component.

Measure task completion, valid structured outputs, invalid plan rates, unnecessary replanning, recovery, policy rejections, latency and total resource cost. Record the model identifier, model version, task schema, sampling settings and supervisory service configuration sufficiently for the tested condition to be understood. Repeated runs should capture variation introduced by stochastic components.

## Resource behaviour and cost

Measure end-to-end completion time as well as individual inference and tool times. Report queue time, timeouts and completion latency at the median, p95 and p99 when the sample size supports those percentiles. Include failed and abandoned requests in the workload accounting.

Record memory use, compute use, task admission, queue growth, throughput and retry volume under a defined load. Report API charges and local resource costs under an explicit accounting method. If energy is measured, identify the measurement boundary and instrument; hardware specifications alone do not establish consumed energy.

Separate cold and warm conditions when initialisation, cache residency or model loading affects results. A lower service latency achieved by rejecting more tasks should be accompanied by the rejection and completion rates.

## Failure, saturation and fallback

Inject failures with a reproducible schedule and record their duration. At minimum, assess unavailable or slow LLM services, invalid supervisory outputs, neural inference overload, exhausted resource budgets, delayed market data, broker disconnection, interrupted storage and process restarts.

For each case, define the expected operating mode and permitted actions before running the test. Observe whether the platform continues an authorised workflow, defers work, reduces scope or abstains. Measure time to detect, time to enter the declared mode, rejected work, lost work and time to reconcile and recover.

Check that fallback preserves execution controls and does not introduce hidden unbounded queues or retry storms. Verify behaviour when a dependency fails during a task, after authorisation and after an execution request whose external outcome is not yet known. Report any period in which the platform could not determine its own effective state.

Successful degraded operation establishes behaviour within the tested envelope. It does not establish uninterrupted autonomy for arbitrary workloads or failures.

## Broker integration

Begin with a provider-supported demo or sandbox environment and a declared adapter version. Verify instrument mapping, permitted operations, authentication lifecycle, request validation, confirmation handling, rejection handling and reconciliation. Check provider-specific limits and account conditions against current official documentation.

Exercise delayed responses, duplicate submissions, uncertain outcomes, partial completion, cancellation races and reconnection. Confirm that repeated or restarted work does not create unintended duplicate external actions. The audit record must support reconstructing what the platform requested and what the broker confirmed.

A demo result should identify the environment and its limits. It does not establish identical live execution behaviour. Capital.com live observations are documented, but the latest recorded passive audit on 16 October 2026 reports stale quotes despite a connected flag, diagnostic timeouts and degraded backend conditions. Verify feed freshness, time consistency and recovery directly; a connection flag is insufficient.

IG and OANDA adapter implementation and mock tests require separate full live qualification. No verified resolution of the recorded Capital.com feed-continuity problem, continuous execution reliability or provider approval is established by this dossier.

## VESPER evaluation remains separate

An inference-runtime study needs its own frozen checkpoint and numerical representation, reference backend, hardware inventory and memory accounting. Verify numerical correctness before comparing latency, throughput or memory behaviour. Measure actual I/O and resource use under the tested workload.

Compare compatible baselines under the same checkpoint, context, workload and budgets. Distinguish the ability to execute from useful completion time. The available VESPER RFC is a design and prior-art analysis; its proposed experiments are not reported here as completed full-model inference results.

## Review package and acceptance

Before evaluation, agree the use case, workload, operating limits and measurable acceptance criteria. Freeze the relevant versions and record permitted changes. Preserve a test manifest, aggregate results, failure cases, audit samples and a comparison against the stated criteria.

Public reporting may disclose reproducible methodology, aggregate measurements and limitations while withholding proprietary model internals and credentials. A confidential technical review may require additional implementation access. Disclosure boundaries should be agreed before testing so that they do not become a reason to omit unfavourable outcomes.

An evidence record should state which tests passed, failed or remain unperformed. Acceptance applies only to the tested scope and does not establish unmeasured deployment performance.
