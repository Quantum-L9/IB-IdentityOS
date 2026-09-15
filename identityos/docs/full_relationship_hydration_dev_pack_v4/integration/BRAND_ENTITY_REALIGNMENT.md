# Brand Entity Realignment

This pack refines the earlier IdentityOS Brand Entity integration model.

## Previous simplification

Earlier framing treated `person | role | brand` too similarly.

## Corrected model

```text
IDENTITY KIND
  human | synthetic_agent | brand | organization

PERSONA
  personal | specialist | brand | character | other governed persona

ROLE
  bounded function performed in a runtime
```

A brand can therefore have many personas:

```text
Acme Brand Identity
  |-- Sales Persona
  |-- Support Persona
  `-- Onboarding Persona
```

Each persona may perform different roles with different tools, policies, and hydration slices.

## Locked consequence

Brand Entity remains valid as a commercial concept, but its platform representation is now:

`Brand Identity + Persona(s) + Role(s) + Policy + Hydration`

There is no separate BrandOS and no dedicated brand persona engine.
