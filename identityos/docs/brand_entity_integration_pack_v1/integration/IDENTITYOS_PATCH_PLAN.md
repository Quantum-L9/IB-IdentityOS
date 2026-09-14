# IdentityOS Integration Patch Plan

## Objective

Integrate Brand Entity as a first-class IdentityOS identity mode while preserving existing repo authority and keeping Phase 1 small.

## Patch Set A: Architecture Law

Update:

- `identityos/README.md`
- `identityos/REPO_SPEC.md`
- `identityos/AGENTS.md`

Add explicit law:

- IdentityOS supports `person | role | brand` identity modes.
- all modes share the same graph, memory admission, hydrator, policy engine, snapshots, eval runner, and adapter rules;
- brand mode references external operational truth instead of owning it;
- BootMyAgent remains the install surface;
- custom packaging remains deferred.

No new runtime service is justified for identity-class dispatch alone.

## Patch Set B: ADRs

Add:

### ADR-008: Identity Classes and Profile Composition

Lock:

- `AgentIdentity` as identity anchor;
- `identity_class` semantics;
- OperationalProfile remains role/domain behavior;
- BrandProfile is additive;
- runtime payloads are derived views;
- lower-precedence context narrows, never expands, authority.

### ADR-009: Brand Truth and Authority Boundary

Lock:

- identity owns identity/policy references;
- authoritative business truth stays external;
- truth bindings carry authority reference, scopes, and freshness policy;
- unavailable material truth fails closed or escalates.

### ADR-010: BootMyAgent Install Contract

Only when `validate` and `hydrate` are proven. Lock install as composition/preflight/adapter binding rather than a new identity authority.

## Patch Set C: Schemas

Modify additively:

- `schemas/agent.schema.json`: optional `identity_class`, optional identity version.
- `schemas/runtime_context.schema.json`: optional channel/requested identity mode if implementation needs them.

Preserve:

- `schemas/profile.schema.json` as OperationalProfile.

Add:

- `schemas/brand_profile.schema.json` from this pack.

Do not make `.aiid` or `.kern` required.

## Patch Set D: Hydrator

Teach the hydrator to resolve identity class and compose:

```text
hard law
-> AgentIdentity
-> class profile
-> operational profile
-> policy/truth bindings
-> RuntimeContext scopes/trust
-> adapter translation
-> eval/preflight
-> RuntimePayload
```

No mode-specific hydrator classes unless implementation evidence later proves a true invariant difference.

## Patch Set E: Website Adapter

Use the existing website chatbot adapter as the first parity fixture.

Required demonstrations:

1. same adapter can hydrate a person identity;
2. same adapter can hydrate a role identity;
3. same adapter can hydrate a brand identity;
4. policy and scope checks remain equivalent across all three;
5. brand-specific facts come through declared truth bindings;
6. adapter cannot mutate identity or durable memory directly.

## Patch Set F: Evals

Add brand evals from `governance/BRAND_GOVERNANCE_AND_EVALS.yaml` to the existing eval runner.

Keep factual blocking gates separate from subjective quality scoring.

## Phase Alignment

### Phase 1: Preserve current scope

Build the currently declared minimum complete IdentityOS system:

- JSON/JSON-LD identity;
- validation;
- memory admission;
- graph write wrapper;
- hydrator;
- policy engine;
- website adapter;
- eval runner;
- `bootmyagent validate`;
- `bootmyagent hydrate`.

Identity class support may be added as schema-compatible metadata if it does not expand the core build materially.

### Phase 2: Role composition

Prove OperationalProfile composition, role switching, domain scope, permission bounds, and replay.

### Phase 3: Brand mode

Add BrandProfile, truth bindings, commercial policy, escalation, and brand eval suite. Prove one customer-facing website surface.

### Phase 4: Install and distribution

Add `bootmyagent install`, versioned install receipts, additional adapters, and organization-level governance only after the underlying contracts are stable.

## Explicit Non-Changes

Do not:

- birth a BrandOS repo;
- add another graph;
- add another memory backend;
- add another policy engine;
- add another hydrator;
- make the website adapter authoritative;
- use a custom file extension as architecture;
- move product/pricing/catalog truth into IdentityOS.
