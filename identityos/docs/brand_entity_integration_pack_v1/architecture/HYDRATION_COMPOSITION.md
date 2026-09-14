# Hydration and Composition Contract

## Objective

Produce the smallest trustworthy runtime view needed by a target substrate while preserving IdentityOS authority boundaries.

## Composition Order

The hydrator resolves inputs in this precedence order:

1. IdentityOS hard invariants and security law.
2. Canonical `AgentIdentity` state from the identity graph.
3. Identity-class profile (`person`, `role`, or `brand`).
4. Operational role/domain profile when present.
5. Policy and authoritative external truth bindings.
6. RuntimeContext trust level and allowed scopes.
7. Channel/target adapter translation.
8. Final policy check and evaluation preflight.
9. RuntimePayload emission.

Lower layers may narrow higher-layer authority but may not expand it.

## Runtime Flow

```text
identity graph
    |
    +--> identity + profile versions
    |
external truth bindings ----+
                             |
policy ----------------------+--> hydrator --> bounded RuntimePayload --> adapter --> substrate
                             |
runtime context -------------+

                          eval/preflight before release
```

## External Truth Bindings

BrandProfile may contain references to authorities such as:

- product/catalog service;
- pricing/offer authority;
- policy documents;
- CRM/customer state;
- billing/order state;
- approved claims registry;
- escalation directory.

A binding is a reference plus scope/freshness policy. It is not a copied system of record.

## Failure Law

Hydration fails closed for a material surface when:

- required identity/profile data is invalid;
- required policy cannot be resolved;
- requested scope exceeds RuntimeContext allowed scopes;
- an authoritative fact binding required for the task is unavailable or stale beyond its declared tolerance;
- adapter output would omit mandatory policy constraints;
- preflight evaluation detects a blocking violation.

A failure in one optional surface must not block unrelated safe surfaces.

## Adapter Law

Adapters may:

- translate RuntimePayload to target syntax;
- map supported capabilities;
- strip unsupported optional fields;
- expose target-specific health/diagnostics.

Adapters may not:

- write durable memory directly;
- mutate canonical identity;
- weaken policy;
- elevate trust;
- invent missing product/offer facts;
- retain secrets beyond the target contract;
- silently add autonomous execution authority.

## Replay

A replayable snapshot must be able to identify the exact identity/profile/policy/runtime/adapter versions used to produce a RuntimePayload. External source values that materially affected the response should carry provenance or snapshot references sufficient for post-hoc reconstruction.
