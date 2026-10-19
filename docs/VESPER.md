# VESPER

**Virtualized Expert Scheduling and Predictive Execution Runtime**

VESPER is System Labs' complementary research track for local inference under constrained memory and I/O resources. It examines execution of a complete mixture-of-experts model when its stored weights exceed available fast memory. The research question is whether a runtime can respect explicit resource budgets, preserve a defined numerical calculation and complete useful inference while accounting for data movement. The available work is RFC 0001, a research design and prior-art analysis.

## The systems problem

Sparse mixture-of-experts inference activates selected experts for a given input. Sparse activation can reduce arithmetic work relative to evaluating every expert, but it does not remove the need to store the model, obtain the required weights and maintain execution state. Memory capacity, data transfer, compute and queueing can impose different limits. An expert absent from fast memory still has to become available before its contribution can be calculated.

The proposed research treats resource admission as part of execution correctness. Work should enter the system only when its required memory and dependencies can be accommodated within a declared budget. That accounting must include model state and runtime buffers, as well as cached weights. A cache miss or an inaccurate prediction should not become an unbounded allocation request. The objective is controlled execution under scarcity, with measured consequences for completion time.

Scheduling must also remain causal. A runtime can use completed observations and measured resource state to decide which work to prepare. It cannot assume knowledge of future routing that depends on calculations not yet performed. Predictive preparation is therefore an optimisation with an error cost. The authoritative model calculation determines which data are required, and incorrect preparation must be reflected in the accounting of resource use and delay.

## Numerical and performance contracts

A numerical contract defines the model representation and the reference calculation against which execution is assessed. Moving weights between memory tiers does not create additional information or automatically preserve every floating-point result. A credible evaluation must define acceptable numerical differences, test actual model operations and distinguish correctness from throughput. Resource optimisation is useful only in relation to that declared calculation.

Capacity and latency are separate outcomes. Establishing that a workload can progress within memory limits does not establish interactive response times. Storage bandwidth, transfer latency, contention and repeated loading may dominate completion time. Evaluation must report observed memory use, data movement, numerical agreement and end-to-end latency against compatible baselines. It must include unfavourable workloads and account for the cost of failed predictions or discarded speculative work.

## Relationship to Multiagentic Platform

Multiagentic Platform concerns coordination of specialist agents, numerical models and controlled actions. VESPER concerns the resource conditions under which an inference service might operate. Their connection is an engineering dependency to investigate, not a completed integration. The portfolio neural model is a separate development component; VESPER's discussion of external model architectures does not describe its structure, size or training.

RFC 0001 does not establish a working full-model runtime, measured inference speedup or validated product-level autonomy. Future claims require an implemented backend, correctness evidence and repeatable measurements. The public research record is available through the [VESPER project](https://giletto-systems-lab.michele-giletto.chatgpt.site/projects/vesper.html) and [RFC 0001](https://giletto-systems-lab.michele-giletto.chatgpt.site/materials/VESPER_RFC_0001.md).
