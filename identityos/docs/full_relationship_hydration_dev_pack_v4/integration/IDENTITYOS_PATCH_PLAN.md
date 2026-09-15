# IdentityOS Patch Plan v4

This is an implementation contract, not proof of implementation.

## Phase 0 - Reconcile current main

Before coding, inspect current `Quantum-L9/IB-IdentityOS` and map existing Identity, OperationalProfile, hydration, policy, trust, memory admission, graph, runtime-context, and eval seams. Do not implement against stale paths from this pack.

## Phase 1 - Lock full relationship hydration invariants

Codify `IDOS-HYD-001` through `IDOS-LEARN-001` as architecture/conformance tests before adding new persistence surfaces.

## Phase 2 - Add archetype contracts

Introduce:

- PersonaArchetype
- UserArchetype
- RelationshipArchetype
- DerivedActorProfile envelope

Do not create new identity kinds.

## Phase 3 - Add preference mirror contracts

Introduce:

- PreferenceEvidence
- PreferenceProfile
- DerivedPreferenceProfile
- EffectivePreferenceProfile

Preserve evidence provenance, confidence, scope, lifecycle, contradiction, and supersession.

## Phase 4 - Implement preference resolver

Implement precedence and receipts. Direct individual evidence must outrank cohort priors. Embeddings may assist retrieval but cannot determine canonical preference value by themselves.

## Phase 5 - Upgrade hydration into two parallel branches

Agent branch resolves/derives Persona. Counterpart branch resolves/derives PreferenceProfile. Synchronize at the full-hydration join barrier.

## Phase 6 - Add EffectiveRelationshipProfile

Compile the agent-side persona, counterpart-side preferences, RelationshipArchetype, Role, Authority, Policy, Trust, Consent, Brand context, and task context into one minimized runtime relationship view.

## Phase 7 - Emit FullHydrationReceipt

Every governed activation must be able to prove what was known, derived, inferred, unknown, overridden, and authoritative at activation time.

## Phase 8 - Wire memory evidence

Use the canonical memory write path for durable preference/relationship evidence. Do not create a second preference database or direct Graphiti write authority.

## Phase 9 - Implement cohort learning behind admission gates

Add privacy-safe cohort aggregation, pattern matching, contradiction analysis, calibration, and versioned DerivedPreferenceProfile promotion. Keep 50-80% cold-start coverage as a measured hypothesis.

## Phase 10 - Prove the executive-gatekeeper fixture

Run Emma + ExecutiveUserArchetype + ExecutiveGatekeeper RelationshipArchetype + DerivedPreferenceProfile through full hydration. Prove that explicit principal preferences override cohort priors.

## Phase 11 - Prove technologified brand divergence

Run Emma and Julie under one brand fixture. Prove brand constraint sharing without persona bleed: Emma remains an internal goal-oriented gatekeeper; Julie remains an outward-facing polite, bubbly, knowledgeable, helpful receptionist.

## Phase 12 - Lock LCTO regression

A runtime with rich agent capability but missing counterpart/relationship hydration must fail full-hydration conformance and may not be labeled "fully hydrated."

## Phase 13 - Compatibility and migration

Migrate historical preference-kernel semantics by classification. Preserve current single-actor paths through adapters until parity tests pass. Do not delete OperationalProfile in the same initial change.

## Explicit exclusions

- workflow orchestration ownership,
- general IAM/ACL redesign,
- direct production deployment,
- unsupported demographic stereotyping,
- cross-customer raw preference sharing,
- public-figure impersonation,
- duplicate memory persistence.
