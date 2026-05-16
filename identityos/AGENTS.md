# AGENTS.md

This file governs all coding agents working in the IdentityOS repository.

## Active Objective

Implement IdentityOS as persistent agent runtime infrastructure.

## Naming Law

Use:

- `IdentityOS` for platform/infrastructure
- `identityos/` for repo root
- `bootmyagent` for CLI command and install surface

Do not reintroduce `CogBoot` unless explicitly requested as a legacy alias.

## Build Law

No placeholders. No fake implementations. No TODO scaffolds masquerading as code.

If a component is not implemented, represent it as a documented phase item, not a stub.

## Phase 1 Scope

Implement only:

- JSON-LD compatible `agent.json`
- local schema validation
- memory admission gateway contract
- Graphiti write wrapper contract
- website chatbot adapter
- local hydrator
- basic policy engine
- basic eval runner
- CLI `bootmyagent validate`
- CLI `bootmyagent hydrate`
- Docker Compose dev stack

`.aiid` and `.kern` are not mandatory in Phase 1.

## Architecture Invariants

```yaml
architecture_invariants:
  graph_is_canonical: true
  continuity_is_externalized: true
  runtime_context_is_ephemeral: true
  durable_memory_single_path: true
  substrate_native_memory_is_scratch_only: true
  handoff_packets_are_views: true
  adapters_are_dumb_translators: true
  hydration_precedes_generation: true
  policy_precedes_execution: true
  consent_precedes_external_sharing: true
  evals_are_mandatory: true
  provenance_is_preserved: true
  trust_is_explicit_not_implicit: true
  custom_extensions_deferred: true
```

## Forbidden

- Direct Graphiti access from adapters
- Durable memory writes to substrate-native notepads
- Full graph exposure to substrates
- Hidden trust escalation
- Raw secret storage in graph
- Required `.aiid` / `.kern` in Phase 1
- Reintroducing duplicate ADR-007
