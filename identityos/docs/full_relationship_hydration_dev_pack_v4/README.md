# IdentityOS Full Relationship Hydration Architecture Dev Pack v4

Status: **LOCKED WEAPONIZED DEV PACK**  
Target repository: `Quantum-L9/IB-IdentityOS`  
Implementation status: **NOT STARTED BY THIS PACK**

## North star

IdentityOS exists to make every governed agent a fully hydrated agent for its specific counterpart and relationship before first interaction, then continuously replace archetypal priors with evidence-backed knowledge of the actual actors and their relationship.

The hydration target is not the agent alone. The hydration target is the **agent-in-relationship**.

```text
                 FULL RELATIONSHIP HYDRATION

        AGENT SIDE                    COUNTERPART SIDE
            |                               |
      AgentIdentity                    Human/Actor Identity
            |                               |
    PersonaArchetype                    UserArchetype
            |                               |
            +--------- RelationshipArchetype --------+
            |                               |
      DerivedPersona              DerivedPreferenceProfile
            |                               |
            +---------------+---------------+
                            |
                 EffectiveRelationshipProfile
                            |
                  Role + Policy + Authority
                            |
                       RuntimeContext
                            |
                       RuntimePayload
```

## Root invariants

1. **Never hand a principal a cold agent.**
2. **Never hand an agent a cold principal or counterpart.**
3. **Cold hydration precedes governed runtime activation.**
4. **Persona and Preference are mirror planes, not the same object.**
5. **RelationshipArchetype is the glue that gives both mirrors their job-specific meaning.**
6. **Derived priors accelerate interaction one but never outrank direct evidence about the actual actor.**
7. **Preferences are executable behavioral state. They are not merely embeddings or retrieval hints.**
8. **Embeddings and Graphiti projections may index or retrieve preference evidence, but they are never canonical preference authority.**
9. **Persona and preference never create role authority, tool permission, consent, or trust.**
10. **Learning improves the next hydration. It does not silently rewrite identity truth.**

## The derivation plane

```text
PersonaArchetype + RelationshipArchetype + Brand/Domain Context + Evidence
    -> DerivedPersona

UserArchetype + RelationshipArchetype + Brand/Domain Context + Evidence
    -> DerivedPreferenceProfile

DerivedPersona + DerivedPreferenceProfile + direct individual evidence
    -> EffectiveRelationshipProfile
```

`DerivedActorProfile` is the generalized derivation envelope. Its specialized projections include `DerivedPersona`, `DerivedPreferenceProfile`, and `DerivedBrandProfile`. It is not a new identity kind.

## Why v4 exists

v3 proved first-class DerivedPersona with `Emma-derived-persona.V1`. That was necessary but incomplete. A richly hydrated Emma can still feel cold if she does not know her principal, the relationship objective, or how the principal wants work handled.

v4 therefore elevates **full relationship hydration** above persona hydration and adds:

- `PersonaArchetype`
- `UserArchetype`
- `RelationshipArchetype`
- `DerivedActorProfile`
- `PreferenceProfile`
- `PreferenceEvidence`
- `DerivedPreferenceProfile`
- `EffectivePreferenceProfile`
- `EffectiveRelationshipProfile`
- full-hydration receipts
- cohort learning and privacy-safe preference derivation
- technologified brand semantics
- executive gatekeeper relationship fixtures
- Julie customer-facing brand agent fixture
- explicit LCTO cold-agent failure regression

## Cold-start coverage hypothesis

The architecture supports a product hypothesis that archetype and cohort evidence may correctly initialize a large fraction of predictable relationship behavior before individual learning. A 50-80% range is retained as an **experimental hypothesis**, not a guaranteed property. Coverage MUST be measured per preference dimension and cohort.

## Start here

1. `ARCHITECTURE_LOCK.yaml`
2. `architecture/FULL_RELATIONSHIP_HYDRATION.md`
3. `architecture/ARCHETYPE_DERIVATION_PLANE.md`
4. `architecture/PREFERENCE_MIRROR.md`
5. `architecture/RELATIONSHIP_ARCHETYPE.md`
6. `architecture/TECHNOLOGIFIED_BRAND.md`
7. `contracts/FULL_HYDRATION_CONTRACT.yaml`
8. `fixtures/executive-gatekeeper-relationship-v1/`
9. `fixtures/julie-brand-receptionist-v1/`
10. `integration/IDENTITYOS_PATCH_PLAN.md`
11. `validation/ACCEPTANCE_GATES.yaml`

Do not treat this pack as proof that these runtime capabilities already exist in the beneficiary repository.
