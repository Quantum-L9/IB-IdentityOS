# Preference Learning and Cohort Refinement

## Individual loop

```text
interaction
-> explicit instruction / correction / acceptance / rejection / repeated behavior
-> PreferenceEvidence
-> candidate preference
-> admission/reconciliation
-> individual PreferenceProfile
-> stronger next hydration
```

## Cohort loop

```text
many privacy-safe relationship outcomes
-> cross-actor pattern analysis
-> support / contradiction / calibration metrics
-> candidate cohort preference
-> cohort admission gates
-> new DerivedPreferenceProfile version
```

## Cohort admission gates

A cohort update SHOULD require:

- minimum cohort size,
- minimum independent support,
- contradiction analysis,
- confidence calibration,
- privacy review,
- outcome evidence where applicable,
- no identifiable cross-customer leakage,
- versioned supersession rather than destructive overwrite.

## Pattern matching

Pattern matching accelerates personalization but does not replace evidence. The system may use a cohort prior on day zero and rapidly dial the profile toward the actual individual as evidence accumulates.
