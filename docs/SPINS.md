# SPINS — Special Instructions

SPINS formalises user defined operating instructions into specialised learned policy components within Multiagentic Platform. Its purpose is to associate a bounded interpretation of an instruction with structured outputs that the native workflow can examine. The inspected build contains multiple SPINS modules, packaged model artifacts and native integration code. SPINS does not depend on an LLM in the inspected `NATIVE_ONLY` configuration.

## From instruction to executable context

An instruction must first become an explicit policy contract: its operating scope, applicable context, permitted contribution and conditions of validity. This step gives training and evaluation a defined reference. A model can be assessed against a specified instruction only when the expected behaviour is sufficiently precise to distinguish agreement, disagreement and unavailable context.

The runtime supplies causal context: information available at the recorded decision time, with its provenance, scope and validity. Context assembled after an outcome cannot retrospectively justify the earlier decision. Account identity, instrument identity and native boundaries constrain where a result applies. These constraints also distinguish a current observation from a cached or incompatible state.

This public description identifies the interfaces and scientific interpretation. It excludes proprietary policy recipes, numerical thresholds, feature definitions and model weights.

## Learned contributions and independent authority

SPINS modules return structured policy proposals or admissibility contributions. A contribution may restrict a proposed entry or supply contextual information to another native component. Its meaning depends on the module's contract; a contextual restriction and an executable order have different authority.

The surrounding workflow independently checks whether a proposal has the required scope, current context, permissions and resources. Authorised execution then passes through a broker adapter. Broker acknowledgements and subsequent observations must be reconciled with the execution record before shared state is treated as confirmed. A learned result therefore participates in a longer decision process whose correctness also depends on state management and external outcomes.

## Artifact identity and documented training

The inspected package contains versioned artifacts with model identity, schema and readiness checks. Cryptographic hashes link packaged models to their recorded identities; the reviewed installed model hashes matched the manifest. This supports traceability between a particular artifact and its associated records, rather than attributing results to an unspecified model revision.

Reviewed training reports document local PyTorch fits on CPU using synthetic examples of approved user policies. These runs concern policy imitation. They do not measure a probability of market profit, prediction of future prices or independent real market performance. No verified GPU training receipt was established for the installed models.

Readiness records report internal fit and software verification. The review inspected those records and selected implementation files; it did not repeat training or rerun the reported tests. The aggregate manifest retains final gates. Artifact integrity, conformity to synthetic policy and operational qualification remain separate evidence categories.

## Fallback and evaluation

The surrounding runtime implements model deadlines, artifact validation and deterministic defaults. Missing, incompatible or late learned output can therefore return an explicit fallback result. Such control paths do not establish uninterrupted operation under arbitrary memory exhaustion, hardware failure or broker disruption.

Qualification should examine instruction conformity on held out cases, causal context construction, scope isolation and rejection of invalid artifacts. Integration tests must then examine stale observations, timeouts, restarts, conflicting proposals and ambiguous external acknowledgements. Comparative evaluation should identify whether the learned component improves the declared task relative to its deterministic reference, including its cost and failure behaviour. Real market evaluation requires its own temporal protocol and outcome record.

The [implementation status](IMPLEMENTATION_STATUS.md) records current evidence and open gates. [Architecture](ARCHITECTURE.md) explains execution boundaries; [validation](VALIDATION.md) defines the broader qualification programme.

## Evaluation and rights

[Technical evaluation and licensing enquiries](../README.md#evaluation-licensing-and-strategic-discussions) can define a bounded review and acceptance criteria. [Voluntary support](../README.md#support) funds independent development under the stated terms.

© 2026 Michele Giletto. All rights reserved. This document grants no licence to implementation source or model assets. See [COPYRIGHT.md](../COPYRIGHT.md).
