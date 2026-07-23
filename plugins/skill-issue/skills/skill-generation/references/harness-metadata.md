# Harness Metadata

Keep the canonical skill portable. When the target harness supports a
host-metadata artifact, put harness-only discovery and invocation
configuration there, at the location and in the format that harness defines.

Create harness metadata only when the confirmed target harness supports it
and the intake contract requires it. Determine the artifact's location,
format, and available fields from the target harness's authoritative
documentation, and check the result against the harness's validator when one
is available. Use only the fields the contract needs.

- Keep human-facing metadata readable and aligned with the skill name and
  the `SKILL.md` purpose.
- When the skill must be invoked explicitly, express that boundary through
  the harness's invocation-policy mechanism.
- When the harness supports no host metadata, or no invocation-policy field,
  the `SKILL.md` description owns the invocation boundary; create nothing.
- Omit optional fields the contract does not require unless the user
  explicitly requests them.

Do not put harness metadata in `SKILL.md`, and do not reuse one harness's
metadata format or fields for another harness.
