# Preference Kernel Migration

Historical preference kernels contain useful semantics but mix too many concerns.

Migrate by classification rather than file copy:

- user communication/output choices -> `PreferenceProfile`
- explicit corrections -> `PreferenceEvidence`
- persona traits -> `Persona` / `PersonaArchetype`
- role restrictions -> `Role`
- operating mode -> `RuntimeContext`
- safety/security constraints -> `Policy`
- tool permissions -> `Authority`
- project/domain procedures -> owning domain system
- learnings/outcomes -> canonical memory evidence

No historical root preference kernel should remain a universal runtime authority after parity and migration evidence exist.
