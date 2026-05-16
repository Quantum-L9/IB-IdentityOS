# Phase 1 Build Scope

Phase 1 proves the IdentityOS thesis with the smallest complete system.

## Implement

```yaml
phase_1:
  schemas:
    - schemas/agent.schema.json
    - schemas/profile.schema.json
    - schemas/runtime_context.schema.json
    - schemas/runtime_payload.schema.json

  services:
    - memory_pipeline/admission_gateway.py
    - identity_graph/graph_write_router.py
    - hydrator/hydrator.py
    - policy/policy_engine.py
    - adapters/website_chatbot/adapter.ts
    - evals/governance.py
    - evals/memory.py

  cli:
    - bootmyagent validate
    - bootmyagent hydrate

  infra:
    - docker-compose.yml
    - Neo4j
    - Postgres + pgvector
    - Redis
    - Temporal
```

## Exclude from Phase 1

```yaml
phase_1_exclusions:
  - mandatory .aiid
  - mandatory .kern
  - robot adapter
  - vehicle adapter
  - enterprise SSO
  - hosted vault
  - node-level signatures
  - SD-JWT governance claims
  - multi-region graph consistency
```

## Acceptance Tests

- Agent JSON validates.
- MemoryCandidate passes admission or quarantine.
- Durable memory write cannot bypass admission gateway.
- Graphiti is accessed only through graph_write_router.
- Hydrator returns scoped RuntimePayload.
- Website adapter preserves policy.
- Native substrate memory is scratch-only.
- Eval detects policy violation.
