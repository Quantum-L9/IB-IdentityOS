# Persona / Preference Mirror

## Mirror law

Persona and PreferenceProfile are mirrored identity projections.

```text
AGENT-SIDE                              COUNTERPART-SIDE
Persona                                 PreferenceProfile
DerivedPersona                          DerivedPreferenceProfile
PersonaEvidence                         PreferenceEvidence
PersonaProvenance                       PreferenceProvenance
Persona compilation                     Preference resolution
Persona eval                            Preference adherence eval
Persona adaptation evidence             Preference learning evidence
```

They are similar, not identical.

Persona answers: **How should this identity naturally think, present, judge, and behave?**

PreferenceProfile answers: **How does this identity want interaction, work, decisions, timing, delegation, and presentation handled?**

## Preference dimensions

A preference profile SHOULD be capable of representing:

- **WHAT**: objectives, priorities, desired outputs, delegated responsibilities,
- **HOW**: communication, format, decision support, working style, escalation style,
- **WHEN**: interruption thresholds, notification cadence, batching, proactive triggers,
- **WHY**: goals, values, optimization preferences, relationship objectives.

## Runtime requirement

Preferences MUST affect runtime behavior through deterministic or auditable resolution. A vector hit or semantic memory result alone does not satisfy this requirement.

The runtime should not have to "remember to search" for known high-confidence preferences. Applicable active preferences are resolved and compiled into the runtime payload before generation or action.

## Learning law

A user correction is high-value `PreferenceEvidence`, not automatic canonical truth. Repeated behavior, rejection, acceptance, and explicit statements may produce candidate preferences. Admission and supersession create stable preference history without silent mutation.
