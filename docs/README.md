# gt-editorial-schema

`gt-editorial-schema` is a small shared editorial contract for GHS-intelligence, BiBLIO, and WRITY.

It does not discover entities, index knowledge, or write content. It only defines the portable shapes, taxonomies, examples, and integration notes that the three projects can agree on.

## What is included

- `schemas/`: JSON Schemas for entities, relationships, sources, and export bundles.
- `taxonomy/`: shared controlled vocabularies for editorial systems.
- `examples/`: small reusable examples for fixtures, tests, and onboarding.
- `docs/`: human documentation for project boundaries and integration.

## Architecture reference

- `EDITORIAL_KNOWLEDGE_GRAPH.md`: future-facing reference for evolving the contract toward an Editorial Knowledge Graph while keeping this repository lightweight and implementation-neutral.

## Contract flow

1. GHS-intelligence discovers entities, relationships, and supporting sources.
2. GHS-intelligence exports an `export_bundle`.
3. BiBLIO imports the bundle and indexes the entities into its knowledge base.
4. WRITY reads trusted entities and relationships to write with better context.

## Stability

The contract should change slowly. Prefer additive changes over breaking ones:

- Add optional fields before requiring new fields.
- Add new taxonomy values without renaming existing IDs.
- Keep examples small enough to copy into tests.
- Move application logic into the consuming projects, not into this repo.

## Suggested usage

Use this repo as a git dependency, submodule, copied contract folder, or pinned release artifact. Each project should pin a known version of the contract and validate its own imports or exports against that version.
