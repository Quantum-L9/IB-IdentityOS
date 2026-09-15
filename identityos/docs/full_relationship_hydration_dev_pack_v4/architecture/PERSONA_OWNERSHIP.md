# Persona Ownership v2

## Canonical decision

**IdentityOS owns personas, including DerivedPersona.**

Applications select and activate personas, but MUST NOT become canonical owners of persona behavioral law when IdentityOS is present.

## Persona responsibilities

IdentityOS SHOULD own:

- PersonaDefinition schema and registry,
- DerivedPersona derivation contract,
- persona versioning and provenance,
- PrincipleSet,
- CognitiveProfile,
- DecisionLens and DomainLens references,
- PresentationProfile,
- InteractionProfile,
- AdaptationPolicy,
- policy/memory/trust bindings,
- role compatibility constraints,
- persona snapshots and replay,
- drift/conformance eval bindings,
- runtime persona compilation.

## Application responsibilities

Applications own persona selection, activation timing, domain workflow, business actions, tools, application state, and domain-specific escalation.

## Identity boundary

```text
source subject(s) -> evidence -> DerivedPersona -> runtime owner Identity -> Role -> Actor
```

A source subject is not automatically the runtime owner identity.

## Persona vs OperationalProfile

Preserve `OperationalProfile` for backward compatibility. Introduce PersonaDefinition as the durable behavioral layer and reduce OperationalProfile toward runtime/role operational binding where appropriate.

## Anti-patterns

Do not implement:

```text
persona = prompt.md + metadata
```

or:

```text
DerivedPersona(source=Jeff Bezos) => Identity(Jeff Bezos)
```

A valid persona remains meaningful without a prompt compiler and never creates source identity equivalence.
