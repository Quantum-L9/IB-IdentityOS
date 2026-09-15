# Multi-Actor Runtime

## Canonical abstraction

IdentityOS supports **N actors <-> N actors**.

The system MUST NOT encode separate top-level architectures for "multi-user" and "multi-agent". Those are cardinality cases of one actor model.

## Example A: many humans, one agent

```text
Human A ---\
            >--- Facilitator Agent
Human B ---/
```

IdentityOS concerns:

- each human identity,
- facilitator persona and role,
- shared vs private context,
- relationship-scoped context,
- consent and visibility,
- minimal hydration.

## Example B: one human, many agents

```text
             |-- CFO Agent
Human -------|-- Architect Agent
             `-- Research Agent
```

Each agent MAY receive a different authorized view of the same human's canonical context.

The CFO need not receive architecture history. The architect need not receive unrelated private financial context.

## Example C: many actors, many actors

```text
Humans / Brands / Organizations
             <->
Multiple governed agents
```

IdentityOS MUST remain agnostic to workflow choreography while preserving:

- actor identities,
- active personas,
- roles,
- relationships,
- trust,
- context visibility,
- consent,
- hydration boundaries.

## Runtime actor binding

Actor instances SHOULD be ephemeral or runtime-scoped references to durable identity/persona/role records.

A runtime binding SHOULD NOT duplicate canonical identity or persona bodies.

## Agent-to-agent relationships

IdentityOS MAY represent relationships such as:

- delegates_to
- may_request_evidence_from
- supervises
- represents

But orchestration, routing, retries, task graphs, and agent workflow execution remain outside IdentityOS.
