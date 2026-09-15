# Relationship Compilation

The final behavior compiler consumes both sides of the mirror.

```text
DerivedPersona
+ EffectivePreferenceProfile
+ RelationshipArchetype
+ BrandIdentity / BrandProfile
+ Role
+ Authority
+ Policy
+ Trust
+ Consent
+ RuntimeContext
+ current task
= EffectiveRelationshipProfile
= minimized RuntimePayload
```

The compiler MUST preserve the origin and confidence of behaviorally material preferences. It MUST be possible to explain whether a behavior came from direct preference, learned relationship evidence, cohort prior, research prior, persona default, or policy.

Historical replay SHOULD pin:

- persona version,
- preference profile version(s),
- relationship archetype version,
- relevant direct evidence snapshot,
- role/policy/trust snapshot,
- compiler version.
