# gt-editorial-schema

`gt-editorial-schema` is the lightweight shared editorial contract for the SEO Articles GT ecosystem.

It does not crawl, write, rank, index, or decide content. It only normalizes how editorial knowledge travels between SKULL, BiBLIO, GHS, and WRITY.

## Phase 1 Flow

```text
SKULL + BiBLIO + GHS -> SCHEMA -> WRITY
```

- SKULL turns spreadsheets, skeletons, and reference articles into structured requirements and structural decisions.
- BiBLIO turns internal reviews, finished articles, and editorial references into stable reusable memory.
- GHS turns fresh external signals into evidence, freshness, and audit trails.
- SCHEMA defines the portable contract.
- WRITY consumes clean normalized context after the upstream systems have organized it.

## Included

- `schemas/`: small JSON Schemas for entities, sources, relationships, bundles, and Phase 1 editorial objects.
- `taxonomy/`: controlled vocabulary used across the ecosystem.
- `examples/`: demo fixtures that show how different inputs become the same auditable language.
- `docs/`: architecture and integration notes.

See `docs/contract-overview.md` for the Phase 1 contract overview.
