# IdentityOS Brand Entity Integration Pack v1.0.0

## Decision

IdentityOS remains the single canonical owner of portable AI identity, continuity, policy, hydration, memory admission, trust, evaluation, snapshots, and runtime adapters.

The Brand Entity concept is integrated as a first-class IdentityOS identity mode alongside person and role. It is not a new platform, memory system, hydration engine, policy engine, graph, or runtime.

BootMyAgent remains the CLI and installation surface for IdentityOS.

## Product Thesis

IdentityOS should support one portable identity architecture with three explicit operating modes:

- `person`: continuity and familiarity for an individual identity;
- `role`: bounded domain/behavior adaptation for a specialist persona;
- `brand`: governed commercial identity across customer-facing surfaces.

The same runtime machinery must hydrate each mode. Differences belong in typed identity/profile contracts and policy, not duplicated infrastructure.

## Core Invariants

1. The IdentityOS identity graph remains canonical.
2. Runtime context remains ephemeral.
3. Durable memory has one admission/write path.
4. Substrate-native memory remains scratch-only.
5. Adapters translate; they do not own identity, memory, policy, trust, or truth.
6. Hydration precedes generation.
7. Policy precedes execution.
8. External business truth remains owned by its authoritative source system.
9. Brand identity may reference product, offer, policy, catalog, CRM, billing, or communication truth, but does not become those systems of record.
10. Person, role, and brand modes must be replayable and evaluable against a frozen identity/runtime version.
11. Custom extensions such as `.aiid` and `.kern` remain deferred packaging standards, not Phase 1 requirements.
12. `.overlay` and `.cont` are not standardized by this pack.

## Integration Outcome

This pack formalizes:

- identity-class semantics;
- profile composition rules;
- brand-specific governance boundaries;
- runtime hydration precedence;
- one-command installation semantics for BootMyAgent;
- brand evaluation requirements;
- phased adoption into the current `Quantum-L9/IB-IdentityOS` repository;
- supersession of conflicting concepts from the source brief.

## Repository Target

`Quantum-L9/IB-IdentityOS`

Current verified architecture baseline used by this pack:

- repository commit observed: `f9fdd090e4dd85a63c6497d34d894e6313ef80a3`
- platform name: `IdentityOS`
- CLI/install surface: `bootmyagent`
- canonical source: portable identity graph
- current Phase 1 files: JSON / JSON-LD

## Pack Status

`ARCHITECTURE_READY_FOR_IMPLEMENTATION_PLANNING`

This pack deliberately stops before code mutation, repository publication, or deployment.

## Suggested Consumption Order

1. `AUTHORITY_MAP.yaml`
2. `architecture/IDENTITY_CLASS_MODEL.md`
3. `architecture/HYDRATION_COMPOSITION.md`
4. `contracts/brand_profile.schema.json`
5. `contracts/BOOTMYAGENT_INSTALL_CONTRACT.yaml`
6. `governance/BRAND_GOVERNANCE_AND_EVALS.yaml`
7. `integration/IDENTITYOS_PATCH_PLAN.md`
8. `validation/ACCEPTANCE_TESTS.yaml`
9. `SUPERSESSION_MAP.yaml`
10. `UNKNOWN_REGISTER.yaml`
