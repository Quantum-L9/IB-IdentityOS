# Full Relationship Hydration

## Decision

IdentityOS SHALL hydrate the **agent-in-relationship**, not merely an isolated agent profile.

A runtime is not fully hydrated until IdentityOS can answer, with provenance and explicit unknowns:

1. Who is the agent?
2. Who is the counterpart?
3. Why are they interacting?
4. What outcome is this relationship optimized for?
5. How should work be divided?
6. How should the agent behave?
7. How does the counterpart prefer work and interaction to happen?
8. What is the agent authorized to know and do now?

## Parallel cold hydration

```text
AGENT BRANCH                            COUNTERPART BRANCH
resolve identity                        resolve identity
resolve PersonaArchetype                resolve UserArchetype
resolve RelationshipArchetype           resolve RelationshipArchetype
resolve brand/domain context            load direct PreferenceEvidence
derive/load DerivedPersona              derive/load DerivedPreferenceProfile
bind role/authority                     resolve EffectivePreferenceProfile
             \                          /
              \                        /
               +------ JOIN BARRIER --+
                         |
                 EffectiveRelationshipProfile
                         |
                 consent/policy/trust
                         |
                     minimization
                         |
              RuntimePayload + Receipt
```

The two branches SHOULD execute independently where implementation permits and MUST synchronize before runtime activation.

## Cold is a failure state

A cold agent knows too little about itself, its job, or its counterpart to behave as "my agent." A cold counterpart model forces the user to re-teach preferences that could have been legitimately inferred from direct history, cohort evidence, relationship archetypes, target-market research, or brand context.

Cold hydration does not authorize invention. It means hydrate everything legitimately knowable and preserve the remainder as explicit Unknown.

## Relationship fluency

Cold hydration creates the best evidence-backed baseline for interaction one. Warm learning then converts priors into principal-specific and relationship-specific knowledge.

```text
cold prior -> interaction -> evidence -> preference/relationship learning -> next hydration
```

The target state is relationship fluency: the agent increasingly knows what the counterpart wants, how they want it, when they want it, what should be suppressed, what should be escalated, and what the agent should own without prompting.
