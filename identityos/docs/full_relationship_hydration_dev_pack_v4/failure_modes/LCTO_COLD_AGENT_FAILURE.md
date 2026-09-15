# LCTO Cold-Agent Failure Pattern

## Source

Operator first-hand deployment lesson supplied during architecture development.

## Failure

An agent can be extensively designed and still fail the first real deployment if activation hydrates only instructions/capabilities and not the agent's identity, counterpart model, preferences, relationship purpose, and operating expectations.

The operator described the first LCTO activation as cold and therefore not experienced as "MY" agent even though the agent had been built intentionally.

## Architecture lesson

The failure was not merely insufficient prompt quality. It exposed the wrong hydration unit.

```text
hydrate agent alone -> capable but relationally cold
hydrate agent + counterpart + relationship -> MY agent
```

## Required regression

No IdentityOS runtime may claim full hydration when any mandatory branch below is absent:

- agent identity/persona,
- counterpart identity/preference baseline,
- relationship archetype,
- role/authority,
- explicit unknowns,
- hydration receipt.

This failure mode is retained as a permanent architecture regression case.
