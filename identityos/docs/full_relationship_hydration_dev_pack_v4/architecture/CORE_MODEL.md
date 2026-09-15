# Core Model v4

## Identity

Identity is the durable referent: **who or what persists across runtimes**.

Initial identity kinds:

- human
- synthetic agent
- brand
- organization

Archetypes and derived profiles are not identity kinds.

## The mirrored planes

Every identity may have two distinct behavioral projections:

1. `Persona`: how the identity naturally presents, reasons, judges, and behaves.
2. `PreferenceProfile`: how the identity wants interaction and work to be performed around it.

They are mirrors, not aliases.

## Archetype plane

- `PersonaArchetype`: reusable agent-side behavioral template.
- `UserArchetype`: evidence-backed target-market/counterpart template.
- `RelationshipArchetype`: job, use case, desired outcome, labor split, risk, and success model for an actor pairing.

## Derived plane

- `DerivedPersona`: agent-side relationship-specific behavioral baseline.
- `DerivedPreferenceProfile`: counterpart-side relationship-specific bootstrap prior.
- `DerivedActorProfile`: generalized derivation envelope that records how a specialized projection was created.
- `DerivedBrandProfile`: technologified brand projection containing approved persona, preference, and relationship references.

## Resolved plane

- `EffectivePreferenceProfile`: resolved preference state after precedence and conflict handling.
- `EffectiveRelationshipProfile`: the joined behavior contract for actual actors in a concrete relationship.

## Runtime plane

- `Role`: bounded function and task authority.
- `Actor`: runtime participant binding Identity to Role and applicable projections.
- `RuntimeContext`: current purpose, task, scope, policy, consent, trust, and authorized context.
- `RuntimePayload`: minimized runtime view, never source of truth.
- `FullHydrationReceipt`: replayable evidence of what was resolved, derived, overridden, unknown, and authoritative at activation.

## Cardinality

The model remains N-actor capable:

```text
1 human <-> 1 agent
N humans <-> 1 agent
1 human <-> N agents
N actors <-> N actors
```

IdentityOS governs identity, persona, preference, relationship, and hydration semantics. It does not become the workflow orchestrator.
