# Multiagentic systems at System Labs

System Labs develops an architectural programme for coordinating specialised software agents across application domains. Multiagentic Platform is its first publicly released application, focused on trading and portfolio workflows. The programme develops from Reasoning Agent and concerns how tasks, observations, computational components and authorised actions can operate within a coherent system.

The reusable element is the coordination architecture. Each application supplies its own domain model, external integrations, permission policies and evaluation criteria. This public dossier describes that programme and its application boundaries. A general purpose SDK or public implementation framework is not part of the current distribution.

## Architectural responsibilities

An agent has a defined responsibility and an operating scope. Depending on the task, its computation may be deterministic software, a numerical service, a learned model or an explicitly enabled language model. The number of language model instances does not define the system's capability. Coordination depends on the contracts between components and the treatment of their outputs.

The programme organises these responsibilities as follows:

| Responsibility | Architectural purpose |
| --- | --- |
| Task coordination | Assign bounded work with declared inputs, expected outputs, dependencies and completion conditions. |
| Capability contracts | Specify the operations a component can perform, the schemas it accepts and the evidence required to consume its result. |
| Scoped context and state | Associate observations and proposals with the relevant user, account, mission or operation so that concurrent work retains a defined context. |
| Permissions | Establish which tools and external actions are authorised within that context, including actions that require explicit user activation. |
| Observation freshness | Track when an observation was obtained and whether it remains suitable for the decision or action under consideration. |
| Model choice | Select a computational path according to the task, available resources, evidence requirements and permitted operating mode. |
| Resource admission | Admit, defer or reject work according to capacity, deadlines, dependencies and the consequences of incomplete execution. |
| Action receipts | Preserve evidence of what an external system accepted, rejected or completed, with enough context to interpret the outcome. |
| State reconciliation | Compare expected and observed state after actions, interruptions or recovery, and resolve uncertainty before dependent work proceeds. |
| Domain adapters | Translate application contracts into the data and operation semantics of each external provider or specialist environment. |

These are architectural responsibilities of the programme. The implementation status and test evidence for a particular product determine which mechanisms are available and qualified in that product.

## From task to observed outcome

A coordinated workflow starts with a bounded objective and observations whose scope and freshness are known. Specialist components produce structured results. The application evaluates those results against its current state, permissions and resource limits before an external action can be admitted.

Execution produces a separate outcome record. An intention, a submitted request and a confirmed result represent different stages. Reconciliation uses the external system's observed state to determine whether subsequent work can proceed, should be retried or must remain suspended. This distinction becomes important when a provider rejects a request, a connection is interrupted or an operation completes only in part.

An optional language model can contribute interpretation, explanation or structured proposals when the application's configuration and evaluation permit it. Authoritative control still depends on the contracts and permissions governing the application. An unavailable model requires an explicitly defined operating response, such as native computation, deferral, reduced task scope or abstention. The validity of that response must be tested for the relevant dependencies and failure conditions.

## First public application: trading

Multiagentic Platform 1.1.25 applies this approach to users' own compatible live broker accounts. Market observations, portfolio state, specialist analysis and proposed decisions share an account context. Native execution controls and broker adapters govern authorised external actions. Users provide their own credentials and explicitly activate trading operation.

The public release uses its native workflow independently of optional language model services. The inspected historical build selects `NATIVE_ONLY`, with the optional LLM paths disabled. The release's package checks and isolated QA are documented separately from live broker qualification in the [release record](releases/1.1.25/README.md) and [implementation status](IMPLEMENTATION_STATUS.md).

SPINS components concern learned instruction policies within this application. The documented CPU training runs use synthetic policy examples. Those records do not establish a generic autonomous agent model or transferable financial performance. Market and account observations in connected use come from the user's broker. [SPINS](SPINS.md), [architecture](ARCHITECTURE.md) and [validation](VALIDATION.md) describe the relevant evidence and limits.

## Planned application: Orbital

Orbital is a separate application within the System Labs portfolio. The development direction is to apply the multiagentic architecture to specialised mission agents operating within Orbital's domain and application state. That integration is planned development work. It is not a feature delivered by the current trading installer.

The shared design concerns coordination, contracts, scoped context, permissions, admission and evidence. Orbital requires its own domain representations, tool contracts, operational constraints and acceptance tests. Broker adapters, trading policies and trading results do not qualify a mission application. The programme's value as a reusable architecture must be demonstrated through those separate integrations and evaluations.

## Evaluation across applications

Each application needs explicit task completion criteria, representative observations, a declared operating envelope and tests for invalid or stale context. Evaluation must examine permission enforcement, component disagreement, partial outcomes, capacity limits and recovery as well as the quality of individual model outputs.

Training and validation remain specific to the task and domain. A successful trading test does not establish Orbital's mission performance. A model's fit to instruction examples does not establish external decision quality. Reuse can reduce duplicated coordination work, while each application retains its own evidence requirements.

VESPER is a complementary inference research programme concerned with execution under constrained memory and data movement. Its published RFC describes a research design; it does not establish an implemented inference service shared by these products. [VESPER](VESPER.md) records that distinction.

The [System Labs technology overview](https://giletto-systems-lab.michele-giletto.chatgpt.site/projects/multiagentic-systems) presents the programme alongside its application portfolio. Implementation details, private training material and industrial recipes remain outside the public dossier.

© 2026 Michele Giletto. All rights reserved. See the repository [copyright notice](../COPYRIGHT.md) and the terms accompanying each distributed application.
