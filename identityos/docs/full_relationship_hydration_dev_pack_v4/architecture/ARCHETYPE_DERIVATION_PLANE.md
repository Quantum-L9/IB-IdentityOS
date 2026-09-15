# Archetype Derivation Plane

## Purpose

Archetypes are reusable evidence-backed templates upstream of concrete profiles. They are factory inputs, not runtime identities.

## Core derivations

```text
PersonaArchetype + RelationshipArchetype + BrandContext + DomainContext + PersonaEvidence
    -> DerivedPersona

UserArchetype + RelationshipArchetype + BrandContext + DomainContext + PreferenceEvidence
    -> DerivedPreferenceProfile
```

`DerivedActorProfile` is the generalized derivation envelope recording archetype refs, evidence refs, confidence, derivation method, conflicts, version, and provenance. Specialized outputs retain their own contracts.

## Target market and use case

A target market is insufficient by itself. `RelationshipArchetype` MUST bind the market to a job-to-be-done and desired outcome.

Example:

```text
Executive
+ AI executive gatekeeper use case
+ protect time / reduce decision load / advance work
= executive_to_ai_gatekeeper RelationshipArchetype
```

This relationship archetype can derive both an Emma-style agent persona and an executive-side preference prior from the same economic context without claiming that every executive is identical.

## Evidence classes

Allowed derivation inputs:

1. direct observed fleet evidence,
2. explicit interviews and first-party research,
3. external validated research,
4. product/operator design intent for agent personas,
5. model inference, clearly labeled and lower authority.

Cohort priors are always probabilistic. No target-market stereotype becomes individual truth merely because it is common in a cohort.

## Coverage hypothesis

The working product hypothesis is that well-selected archetypes may initialize a material portion of predictable user interaction preferences before individual learning. The current 50-80% idea is an experimental range to measure, never a guaranteed requirement.

Measure per dimension:

- cold-start acceptance rate,
- immediate override rate,
- preference overlap,
- cohort stability,
- time-to-personalization,
- contradiction rate,
- calibration error.
