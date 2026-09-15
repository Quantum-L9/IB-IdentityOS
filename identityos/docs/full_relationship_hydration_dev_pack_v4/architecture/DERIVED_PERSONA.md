# DerivedPersona

## Canonical decision

`DerivedPersona` is a first-class **persona derivation construct** inside IdentityOS.

It is not:

- a `DerivedPerson`,
- an identity kind,
- a clone claim,
- a representation that the runtime actor is the source human,
- an authority grant,
- a prompt blob.

## Source model

A DerivedPersona MAY derive from:

1. one source subject,
2. multiple source subjects,
3. source documents without a named subject,
4. one or more existing PersonaDefinitions,
5. explicitly synthetic components.

Every derived component MUST retain source-level provenance or be explicitly marked `SYNTHETIC`/`UNVERIFIED`.

## Component model

A DerivedPersona may compose:

- principles,
- cognitive patterns,
- decision lenses,
- domain lenses,
- presentation behavior,
- interaction behavior,
- contextual adaptation behavior.

Components MAY have different sources. Composition therefore occurs at component level, not by concatenating full persona prompts.

## Representation modes

Recommended initial modes:

- `SOURCE_DERIVED`
- `COMPOSITE_DERIVED`
- `SYNTHETIC`

A public-figure-informed persona is `SOURCE_DERIVED` or `COMPOSITE_DERIVED`; the source figure remains provenance only.

## Identity boundary

Correct:

```text
Identity: synthetic_agent_001
Persona: derived_bezos_customer_obsession@2
Source subject: Jeff Bezos
```

Incorrect:

```text
Identity: Jeff Bezos
Runtime actor claims to be Jeff Bezos
```

unless the actual authenticated human identity is truly that person, which is outside the derived-persona mechanism.

## Authority boundary

DerivedPersona MAY affect behavioral selection and presentation.

DerivedPersona MUST NOT independently:

- expand tool permissions,
- widen memory visibility,
- raise trust level,
- bypass consent,
- override role boundaries,
- override policy,
- claim source endorsement.

## Provenance rule

Trait-level or lens-level provenance is preferred over one opaque source list for the entire persona. A future audit must be able to answer:

> Why does this persona contain this principle/lens/style rule, and what source supports it?
