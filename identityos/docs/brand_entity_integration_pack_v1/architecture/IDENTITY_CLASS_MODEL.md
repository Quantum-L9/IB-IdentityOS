# Identity Class Model

## Purpose

Add explicit `person | role | brand` semantics without creating three infrastructure stacks.

## Canonical Model

```text
AgentIdentity
  |
  +-- identity_class: person | role | brand
  |
  +-- canonical identity graph state
  |
  +-- zero or more bounded profiles
        |
        +-- OperationalProfile
        +-- BrandProfile
        +-- future domain-specific profile types
```

`AgentIdentity` remains the durable identity anchor. Profiles narrow or shape behavior for a specific operating mode. Runtime payloads are derived views.

## Mode Contracts

### Person

Purpose: preserve a specific individual's portable identity, familiarity, preferences, continuity, policy, and memory boundaries.

Composition:

```yaml
mode: person
requires:
  - AgentIdentity(identity_class=person)
optional:
  - OperationalProfile
  - scoped domain context
```

Must not imply delegated authority merely because familiarity is high.

### Role

Purpose: produce a bounded specialist persona with explicit domain, permissions, task behavior, and escalation limits.

Composition:

```yaml
mode: role
requires:
  - AgentIdentity(identity_class=role)
  - OperationalProfile
constraints:
  - permissions must be explicit
  - role scope must not exceed runtime trust or allowed scopes
  - domain context must not mutate canonical identity authority
```

### Brand

Purpose: express a governed commercial identity consistently across customer-facing surfaces.

Composition:

```yaml
mode: brand
requires:
  - AgentIdentity(identity_class=brand)
  - BrandProfile
optional:
  - OperationalProfile
  - channel profile
  - domain context
constraints:
  - business facts resolve from authoritative sources
  - claims and offers are policy-bound
  - escalation is explicit
  - channel adapter cannot redefine brand law
```

## Why Brand Is an Identity Class

Brand identity has durable identity semantics: name, voice, values, interaction style, presentation constraints, customer promise, prohibited behaviors, and governance. These are not merely prompt decoration.

But brand identity does not own every business fact the brand discusses. Product availability, pricing, offers, account data, policy documents, order state, and similar operational facts belong to their source systems and are hydrated by scoped reference.

## Identity / Profile Separation

Identity answers: **who is this agent representation?**

Profile answers: **how may this identity behave in this context?**

RuntimeContext answers: **what substrate, trust, scopes, and session conditions apply now?**

RuntimePayload answers: **what exact bounded view may the target runtime receive?**

This separation prevents a role switch, campaign, or website channel from silently rewriting canonical identity.

## Versioning

Every hydrated execution should be attributable to:

- identity version;
- profile version;
- policy version;
- source binding versions or freshness markers when material;
- runtime context version/receipt;
- adapter version;
- evaluation result or preflight receipt when required.

Versioning exists for replay and drift diagnosis, not decorative metadata.
