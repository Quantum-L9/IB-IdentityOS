# REPO_SPEC.md

## Product Boundary

IdentityOS owns continuity, policy, hydration, memory admission, scoped runtime context, trust, evals, snapshots, and adapters.

IdentityOS does not own base model inference, substrate runtime execution, or native provider memory.

## Corrected Repository Shape

```text
identityos/
  README.md
  AGENTS.md
  REPO_SPEC.md
  ADR_INDEX.md
  PHASE_1_BUILD_SCOPE.md
  docs/
    ADR/
    ARCHITECTURE.md
    MEMORY_ARCHITECTURE.md
    HYDRATION_PROTOCOL.md
    TRUST_LADDER.md
    ADAPTER_AUTHORING_GUIDE.md
  schemas/
    agent.schema.json
    profile.schema.json
    runtime_context.schema.json
    runtime_payload.schema.json
    jsonld/context/v1.jsonld
  memory_pipeline/
  identity_graph/
  vault/
  coherency/
  snapshot/
  hydrator/
  adapters/
  policy/
  workers/
  server/
  sdk/
  cli/
  validator/
  evals/
  infra/
  examples/
  conformance/
  security/
  scripts/
  tests/
```

## Critical Correction

The uploaded complete file tree is canonical as target architecture, but Phase 1 must not require custom extensions.

Use `agent.json` and JSON-LD internally. `.aiid` and `.kern` remain deferred standardization artifacts.
