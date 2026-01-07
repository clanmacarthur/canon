# Main App Handoff - Ready

All required files already exist in this repo. No new folders or copies are needed.

## Files to use

- 00_MASTER_HANDOVER/SystemManifest.md
  - Source of truth for table purpose, level, runtime, and dependencies.
- 00_MASTER_HANDOVER/RelationsManifest.md
  - FK edge list and derived many-to-many relations.
- 00_MASTER_HANDOVER/TableIndex.md
  - Full table list with columns, PK, and FK details.
- 00_MASTER_HANDOVER/SeedPack.md
  - Seed row definitions for presets and blueprints.

## SQL artifacts

- 02_CANONICAL_SCHEMAS/schema_missing_tables.sql
  - Note only; no migration needed (execution tables already exist).
- 02_CANONICAL_SCHEMAS/seed_blueprints_and_presets.sql
  - Seed inserts for timing presets, narration styles, transition rules,
    cue triggers, and session blueprints.
  - Wire into the seed workflow after canonical tables exist; idempotent
    (WHERE NOT EXISTS) and safe for dev/test (prod if desired).

## Required schema awareness for Main App

- session_runs uses session_template_id (text). No blueprint_id column.
- session_outputs uses output_data (jsonb) and version. No content_text column.
- session_output_text table does not exist.
- session_blueprints.lens_preset_id is uuid, meta_lens_presets.id is bigint
  (no direct FK; seeded rows leave lens_preset_id NULL).
- Canonical boundary: Main App writes user-state tables only; canonical
  libraries are read-only at runtime.

## Seed verification (current)

- timing_presets = 3
- narration_styles = 3
- transition_rules = 3
- cue_triggers = 6
- session_blueprints = 6
