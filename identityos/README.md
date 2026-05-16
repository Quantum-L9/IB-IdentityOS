# IdentityOS

IdentityOS is persistent agent runtime infrastructure.

It transforms generalized frontier model capability into governed, continuity-preserving, context-aware operational agent behavior through graph-backed contextual prior shaping.

IdentityOS is not a chatbot, not a model, not a runtime replacement, not prompt storage, and not generic memory. It is the identity, continuity, policy, hydration, and portability layer above model and substrate runtimes.

BootMyAgent is the CLI and install surface for IdentityOS.

## Canonical Naming

```yaml
repo_root: identityos/
platform: IdentityOS
cli_surface: bootmyagent
custom_extensions:
  phase_1_required: false
  deferred_standardization:
    - .aiid
    - .kern
```

## Phase 1 Rule

Phase 1 uses normal JSON / JSON-LD files:

```text
agent.json
profile.json
runtime_context.json
runtime_payload.json
```

`.aiid` and `.kern` are not required in Phase 1. They are deferred standardization artifacts.

## Core Architecture

```yaml
IdentityOS:
  canonical_source:
    portable_identity_graph

  memory:
    single_canonical_durable_pipeline

  runtime:
    scoped_hydration

  governance:
    policy_before_generation
    policy_before_execution

  adapters:
    dumb_translators

  evals:
    required_for_drift_governance_memory_role

  snapshots:
    replayable_runtime_state
```

## Hard Invariants

- Graph is canonical.
- Runtime context is ephemeral.
- Durable memory has one canonical write path.
- Native substrate memory is scratch only.
- Substrates receive scoped slices only.
- Adapters never own memory, identity, policy, or trust.
- Handoff packets are runtime views, not source of truth.
- `.aiid` / `.kern` are deferred, not Phase 1 requirements.
