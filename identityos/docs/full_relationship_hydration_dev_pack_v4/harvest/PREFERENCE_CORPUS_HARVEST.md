# Preference Corpus Harvest

## Sources reviewed

Uploaded/current-conversation sources:

- `preferences_kernel.v1.yaml`
- `Igor_Beylin_Preferences_v4.5.yaml`
- `06_user_preferences_identity.kernel(1).yaml`
- `06_user_preferences_identity.kernel.compiled.yaml`
- `boss_preferences(1).md`
- `preference_extractor_schema.yaml`
- `index_preferences.py`
- `Kernel - Master User Preferences(3).md`
- two Manus agent-development analysis documents

Dropbox folder reviewed:

`/L9 Constellation - NODES/PromptOS/UNIFIED_PROMPT_TOOLKIT/DEPRECATED/USELESS/09_DATA_RESOURCES/04_User_Preferences/`

All six filenames containing `preference` were read:

- `preference-aware-agent.prompt.md`
- `preference-diff-tracker.prompt.md`
- `preference-clusterer.prompt.md`
- `preference-summarizer.prompt.md`
- `preference-file-template.md`
- `preference-index-generator.prompt.md`

All six Dropbox files are deprecated placeholder-only artifacts. Their implementation is rejected. Their lifecycle vocabulary is retained as historical design evidence: preference-aware behavior, clustering, summarization, indexing, drift/diff tracking, and standardized representation.

## Accepted semantics

1. Preferences are structured state with strength, scope, trigger/enforcement, and provenance.
2. Explicit corrections are high-value preference evidence.
3. Preference drift and supersession must be modeled rather than mutating one blob.
4. User preferences must alter agent behavior, not merely be retrievable text.
5. Relationship-specific preferences are distinct from global user preferences.
6. Operating mode is runtime state, not itself a preference, though users may prefer a mode.
7. User preference models must remain subordinate to safety, policy, consent, role authority, and current explicit instruction.
8. Embedding preference text is useful for retrieval but insufficient as canonical preference state.

## Rejected legacy machinery

- root "preference kernel" that simultaneously owns identity, persona, role, reasoning, policy, workflow, and authority,
- all-sections-must-load prompt bundles,
- PacketEnvelope-era memory concepts,
- fixed 0.9 confidence for arbitrary preference packets,
- first-100-character deduplication as semantic identity,
- direct store/projection writes that bypass canonical memory admission,
- preference = embedding,
- hidden chain-of-thought persistence requirements,
- unsupported performance claims from historical prompt packs.

## Manus documents

The Manus documents contribute structural ideas around multi-layered persona, relationship modeling, behavioral learning, policy enforcement, and outcome feedback. Claimed institutional/credential metadata is not treated as verified authority by this pack.
