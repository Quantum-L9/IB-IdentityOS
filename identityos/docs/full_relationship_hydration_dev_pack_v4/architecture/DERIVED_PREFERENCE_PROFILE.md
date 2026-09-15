# DerivedPreferenceProfile

## Definition

A `DerivedPreferenceProfile` is a versioned, provenance-bound, probabilistic bootstrap model of how a user/cohort is likely to want an agent to work with them in a particular relationship.

It is the user-side twin of `DerivedPersona`.

## It is not

- an individual preference fact,
- a stereotype promoted without evidence,
- a replacement for explicit user preferences,
- a permission grant,
- a vector embedding,
- a silent behavior modifier without receipt.

## Lifecycle

```text
cohort/research evidence
      -> DerivedPreferenceProfile prior
      -> cold hydration
      -> interaction
      -> PreferenceEvidence
      -> CONFIRMED / OVERRIDDEN / CONTESTED / REMAINS_PRIOR
```

## Individual evidence wins

The system MUST allow an actual principal to diverge sharply from cohort expectations. A confirmed individual preference supersedes the applicable cohort prior for that individual and scope.

## Cohort learning

Privacy-safe aggregate evidence from many relationships may update a cohort profile. Identifiable facts from one customer MUST NOT become visible to another customer through the derived profile.
