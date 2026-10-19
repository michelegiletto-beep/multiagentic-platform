# Public architecture

This document describes the target architecture of Multiagentic Platform. It provides a technical account of the programme while withholding proprietary model structure, training recipes, resource thresholds and implementation details. Implementation and end-to-end behaviour require separate evaluation.

## Product lineage and system boundary

Multiagentic Platform develops the Reasoning Agent programme into a shared environment for specialist agents, numerical models and controlled actions. Its first application is portfolio allocation. The public boundary includes observations, analytical outputs, proposed decisions, execution controls and the evidence connecting them.

VESPER is a complementary inference research programme. It examines how a fixed model representation might be executed within explicit memory and I/O budgets when the complete weights cannot reside in fast memory. It is not the portfolio neural model, evidence of that model's parameter count or proof that the platform can already run a large model locally. The available VESPER RFC remains a research design.

## Why the system requires more than model inference

Market observations arrive through time and may be revised, delayed or absent. Portfolio state changes as actions are accepted, rejected or partially completed. Agents can produce individually coherent results that rely on different observations or incompatible assumptions. Inference also consumes finite memory, compute and service capacity.

These interactions create coupled correctness requirements. A prediction must use information available at its decision time. A proposed allocation must correspond to a known portfolio state. A task must have defined inputs, permitted tools and a deadline. An action must remain authorised when execution occurs. Resource management must preserve these conditions during degraded operation.

The relevant complexity is therefore temporal, statistical and operational. Public descriptions of model size alone cannot establish scientific merit, predictive validity or system reliability.

## Statistical and neural component

The neural modelling programme uses market histories and statistical features within explicit training and evaluation windows. The developer reports training on privately owned GPU infrastructure. This dossier does not include training logs, measured compute, hardware topology, parameter counts or independently reproduced model results.

The numerical component is intended to return structured estimates accompanied by the model identity, input provenance and applicable validity conditions. Data preparation, fitting and evaluation must preserve the timing of information availability. Estimates require calibration and comparison with suitable statistical baselines before they can support an allocation claim.

The internal network structure, feature engineering recipe, optimisation settings and trained weights remain proprietary. Their omission from this public dossier does not replace the need for evidence: an evaluation should provide sufficient controlled access or measurement records to test the claims under review.

## LLM supervisory orchestrator

The proposed LLM supervisor operates over an explicit task interface. It can interpret a request, select permitted analytical tasks, form a bounded plan and combine structured results. Task contracts should identify required inputs, allowed operations, output types, resource limits and completion conditions.

An LLM is useful at this layer when coordination requires interpreting heterogeneous evidence and adapting a plan to a changing context. Its contribution must be established against simpler orchestration baselines. Adding an LLM can also introduce latency, cost, invalid outputs and inconsistent plans; these are measurable engineering costs.

Numerical estimates remain the responsibility of their identified models and analytical services. The supervisory layer should request those estimates and preserve their provenance. The deterministic control layer should independently validate task structure, permissions, deadlines and proposed state transitions before consequential actions proceed.

The design does not depend on interpreting fluent language as proof of numerical correctness or authority. Structured outputs still require validation. Replanning must preserve the applicable limits and invalidate decisions whose required context has materially changed.

## Bounded autonomous and degraded operation

Autonomy is an operating envelope: a declared set of tasks, permissions, resources and recovery behaviours. The intended platform should continue only within that envelope when an optional supervisory service becomes unavailable or saturated.

The proposed control path includes bounded admission, explicit deadlines, limited retries and a policy for reducing workload. Resource pressure may require deferring new work, using an already authorised deterministic workflow, reducing analytical scope or abstaining from a new action. The appropriate response depends on the cause of degradation and the evidence still available.

An LLM outage and neural inference saturation are distinct failures. A policy that tolerates the former may still depend on a functioning numerical service. If the numerical service cannot produce a valid estimate, the control path must use an explicitly authorised alternative or suspend the dependent decision. It cannot assume equivalent predictive quality from a reduced workload or an unavailable model.

Order admission, state reconciliation, permission enforcement and audit recording must remain effective during degraded operation. A claim of autonomous continuity requires fault-injection tests that show what completed, what was deferred, what was rejected and how state was recovered. No such completed end-to-end test record is supplied with this dossier.

## Broker adapter boundary

Capital.com is a candidate integration target. A provider adapter would translate the platform's authorised requests into that broker's account, instrument and execution semantics. Other brokers require their own compatibility assessment. A common adapter interface does not make provider behaviour interchangeable.

The integration path should begin in a broker-supported demo or sandbox environment. It should verify authentication, instrument identity, market data timing, order validation, request outcomes, reconciliation, cancellation and recovery. Supported products, account permissions, geographic availability, API limits and execution rules must be checked against the provider's current documentation and the intended account.

The broker boundary should retain credentials outside model prompts and restrict the supervisor to permitted operations. Request tracking, duplicate prevention and reconciliation should be verified under delayed responses, lost connections, partial completion and process restarts. When a response is uncertain, the platform should establish the broker's current state before deciding whether another request is appropriate.

Progression to a live account requires an account-specific evaluation and explicit operating authorisation. No existing verified Capital.com adapter, completed live execution integration, provider partnership or endorsement is asserted here. Portfolio research results would not by themselves validate execution through any broker.

## Audit and recovery

The target audit record links an observation and its timestamp to model versions, task requests, structured results, plan revisions, policy decisions, execution requests and reconciled outcomes. It should distinguish a proposed action from an authorised request and a confirmed external outcome.

Recovery should begin from durable records and reconciled external state. Tests must establish how interrupted tasks, uncertain execution outcomes and stale permissions are handled. The public validation protocol defines the evidence needed to evaluate those behaviours without disclosing proprietary algorithms.

## Relationship to VESPER

The platform and VESPER share a resource-management question: which work can be admitted and completed within an explicit operating budget? Their evidence remains separate. A portfolio prediction study cannot validate an inference runtime, and a memory feasibility result cannot establish portfolio performance.

VESPER's public work distinguishes memory capacity, numerical fidelity and response latency. Future integration would need to establish model compatibility, numerical correctness, resource accounting and service behaviour under actual platform workloads. The present RFC does not establish those integration results.
