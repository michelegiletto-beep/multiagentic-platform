# Validation protocol

This protocol specifies how Multiagentic Platform can be evaluated without publishing proprietary model recipes or trading logic. It is an evaluation plan. The tests and acceptance gates below are not presented as completed results.

## Evidence categories

Every externally stated claim should identify its scope and supporting record. A public description verifies what has been stated, not that its implementation has been inspected or its behaviour reproduced.

| Category | Evidence available in this dossier | Permitted conclusion |
| --- | --- | --- |
| Public source record | Platform description and VESPER RFC | The programme, research questions and stated status are documented. |
| Developer report | First software release prepared; training uses developer-owned GPUs | These are reported development facts, without supporting release inspection or training logs here. |
| Proposed architecture | Typed tasks, bounded LLM plans, deterministic controls, degraded operation and broker adapters | These are design targets awaiting implementation and evaluation evidence. |
| Measured platform result | No complete end-to-end platform result supplied | No validated autonomy, broker execution, predictive advantage or investment return follows from this dossier. |

A future result record should name the tested software and model versions, environment, workload, comparison conditions, exclusions, measurements and uncertainty. Independent review should distinguish source inspection, developer-run tests and reproduced results.

## Temporal data and leakage control

Define the decision time and the information genuinely available at that time. Preserve publication delays, revisions, market calendars and the timing of corporate actions. A historical value stored in a modern database may differ from the value available to an earlier decision.

Partition training, model selection and final evaluation in chronological order. Fit transforms, feature selection, imputation and calibration using only the permitted training history. Where labels or samples overlap across windows, define an exclusion or embargo policy appropriate to that overlap before final evaluation.

Use a point-in-time instrument universe when a universe is part of the experiment. Document survivorship, delistings, missing observations and unavailable instruments. Keep final evaluation periods separate from model selection. Repeated inspection of a held-out period should be recorded as an additional selection decision.

Use rolling or expanding temporal evaluation when it matches the intended deployment. Report each evaluation window and variation across market conditions. A single favourable interval is insufficient to establish stability.

## Numerical models and decision quality

Specify the prediction target, horizon and intended use before choosing metrics. Evaluate numerical error, calibration and ranking or classification quality only where relevant to that target. Compare against simple persistence, statistical and other suitable baselines using the same data availability rules.

Distinguish prediction quality from allocation quality. An allocation study requires its own reference policy, exposure constraints and execution assumptions. If transaction costs, slippage, market impact, financing or product-specific charges are relevant, include and stress them explicitly. Avoid interpreting a frictionless historical simulation as evidence of attainable execution results.

Report uncertainty, failed cases and sensitivity to reasonable assumptions. Document all material model selection and repeated testing. This repository makes no profitability, expected return or financial suitability claim.

## Orchestration baselines and ablations

Compare the proposed system with a fixed workflow, a deterministic rule-based scheduler and an appropriate non-LLM allocation method. Keep inputs, numerical services, permissions and resource budgets comparable. Where budgets differ, report that difference rather than attributing the entire result to orchestration.

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

A demo result should identify the environment and its limits. It does not establish identical live execution behaviour. Capital.com remains a proposed adapter target in this dossier; no completed compatibility or live account result is supplied.

## VESPER evaluation remains separate

An inference-runtime study needs its own frozen checkpoint and numerical representation, reference backend, hardware inventory and memory accounting. Verify numerical correctness before comparing latency, throughput or memory behaviour. Measure actual I/O and resource use under the tested workload.

Compare compatible baselines under the same checkpoint, context, workload and budgets. Distinguish the ability to execute from useful completion time. The available VESPER RFC is a design and prior-art analysis; its proposed experiments are not reported here as completed full-model inference results.

## Review package and acceptance

Before evaluation, agree the use case, workload, operating limits and measurable acceptance criteria. Freeze the relevant versions and record permitted changes. Preserve a test manifest, aggregate results, failure cases, audit samples and a comparison against the stated criteria.

Public reporting may disclose reproducible methodology, aggregate measurements and limitations while withholding proprietary model internals and credentials. A confidential technical review may require additional implementation access. Disclosure boundaries should be agreed before testing so that they do not become a reason to omit unfavourable outcomes.

An evidence record should state which tests passed, failed or remain unperformed. Acceptance applies only to the tested scope and does not establish unmeasured deployment performance.
