# gt-editorial-schema

`gt-editorial-schema` is a small shared editorial contract for SKULL, GHS-intelligence, BiBLIO, and WRITY.

It does not discover entities, index knowledge, make content decisions, or write content. It only defines the portable shapes, taxonomies, examples, and integration notes that the ecosystem can agree on.

## What is included

- `schemas/`: JSON Schemas for entities, relationships, sources, Phase 1 editorial objects, and export bundles.
- `taxonomy/`: shared controlled vocabularies for editorial systems.
- `examples/`: small reusable examples for fixtures, tests, and onboarding.
- `docs/`: human documentation for project boundaries and integration.

## Architecture reference

- `EDITORIAL_KNOWLEDGE_GRAPH.md`: future-facing reference for evolving the contract toward an Editorial Knowledge Graph while keeping this repository lightweight and implementation-neutral.
- `contract-overview.md`: Phase 1 overview for how SKULL, BiBLIO, and GHS normalize different inputs into the same auditable language.

## Contract flow

1. SKULL converts spreadsheets, skeletons, and reference articles into `editorial_requirement`, `content_block`, and `skeleton_decision` objects.
2. BiBLIO converts internal reviews, finished articles, and editorial references into `editorial_entity`, `reusable_note`, and `source_ref` objects.
3. GHS converts fresh external signals into `freshness_signal`, `evidence_item`, and `audit_log` objects.
4. The schema normalizes those objects into portable bundles.
5. WRITY consumes clean normalized context after it has been structured upstream.

## Stability

The contract should change slowly. Prefer additive changes over breaking ones:

- Add optional fields before requiring new fields.
- Add new taxonomy values without renaming existing IDs.
- Keep examples small enough to copy into tests.
- Move application logic into the consuming projects, not into this repo.

## Suggested usage

Use this repo as a git dependency, submodule, copied contract folder, or pinned release artifact. Each project should pin a known version of the contract and validate its own imports or exports against that version.
