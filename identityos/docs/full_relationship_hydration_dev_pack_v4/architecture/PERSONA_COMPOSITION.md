# Persona Composition

## Principle

Composition operates on typed persona components, not whole-prompt inheritance.

A DerivedPersona MAY combine components from different sources:

```text
CognitiveProfile  <- source A
DecisionLens      <- source A + source B
Presentation      <- source C
Interaction       <- synthetic policy
DomainLens        <- verified knowledge source
```

## Conflict handling

Conflicting components MUST NOT be silently merged. The composed persona must record one of:

- explicit precedence,
- scoped applicability,
- unresolved conflict that blocks that component,
- synthetic reconciliation with provenance.

## Composition provenance

Every composed component must retain:

- source refs,
- extraction/derivation method,
- confidence/verification state,
- transformation notes when applicable,
- version.

## Role separation

Composition never creates authority. A persona that contains a financial decision lens does not become authorized to act as a financial officer unless Role/Policy explicitly permit that function.
