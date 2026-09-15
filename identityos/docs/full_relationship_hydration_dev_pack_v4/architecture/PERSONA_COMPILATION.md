# Persona Compilation v4

Persona compilation remains task-scoped, minimized, provenance-preserving, version-bound, and replayable.

It is now one branch of full relationship hydration.

```text
PersonaArchetype / PersonaDefinition / DerivedPersona
+ RelationshipArchetype
+ Role
+ BrandContext
+ task/purpose
+ Policy/Trust
-> minimized agent-side persona slice
```

The persona slice then joins an `EffectivePreferenceProfile` before the final runtime relationship payload is emitted.

Persona compilation MUST NOT:

- consume a cohort preference prior as if it were an agent trait,
- grant role or tool authority,
- inject the entire persona dossier when a smaller slice is sufficient,
- erase provenance or version references.
