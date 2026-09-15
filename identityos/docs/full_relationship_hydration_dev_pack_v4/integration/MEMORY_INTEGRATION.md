# Memory Integration

IdentityOS SHALL not create a duplicate memory substrate for preferences.

## Boundary

IdentityOS owns:

- PreferenceProfile semantics,
- DerivedPreferenceProfile semantics,
- PreferenceEvidence admission requirements,
- preference resolution precedence,
- relationship hydration,
- behavior compilation receipts.

The canonical memory service owns durable persistence of admitted immutable evidence through its existing write path.

Graphiti and embeddings may project/index:

- preference evidence,
- cohort patterns,
- relationships,
- semantic similarity.

They MUST NOT become canonical preference authority.

## Outcome-evidenced loop

```text
resolved preference
-> agent behavior
-> observable outcome / user correction / acceptance / rejection
-> immutable evidence
-> candidate preference or cohort update
-> governed admission
-> stronger next hydration
```

This composes directly with Outcome-Evidenced Memory while preserving the rule that memory stores evidence and IdentityOS owns identity/relationship semantics and runtime resolution.
