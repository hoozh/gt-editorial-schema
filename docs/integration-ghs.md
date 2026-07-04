# Integration: GHS-intelligence

GHS-intelligence is the discovery side of the contract.

## Responsibility

GHS should identify candidate entities, normalize them into `entities.schema.json`, connect them through `relationships.schema.json`, and attach source references through `source.schema.json`.

## Export shape

When GHS sends data to another project, it should produce an object that follows `schemas/export_bundle.schema.json`.

Minimum useful export:

- `schema_version`
- `generated_by`
- `generated_at`
- `entities`
- optional `relationships`
- optional `sources`

## Guidance

- Use stable entity IDs like `brand:coinpoker`, `event:wsop`, or `topic:crypto-poker`.
- Mark uncertain discoveries as `draft`.
- Include `source_ids` whenever a fact or relationship depends on evidence.
- Avoid adding GHS-only fields to the shared object. Keep project-specific metadata outside the bundle or under a separate local wrapper.
