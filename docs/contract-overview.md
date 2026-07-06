# Contract Overview: Phase 1

`gt-editorial-schema` is the shared contract for the Phase 1 SEO Articles GT ecosystem. It is not a framework, service, database, crawler, prompt library, or writing engine.

The contract answers one question: how does editorial knowledge travel in a small, portable, auditable shape?

## Flow

```text
SKULL + BIBLIO + GHS -> SCHEMA -> WRITY
```

## Roles

### SKULL

SKULL converts spreadsheets, skeletons, and reference articles into requirements and structural decisions.

It may produce:

- `editorial_requirement`
- `content_block`
- `skeleton_decision`

SKULL does not write final articles.

### BIBLIO

BIBLIO converts internal reviews, finished articles, and editorial references into stable memory.

It may produce:

- `editorial_entity`
- `reusable_note`
- `source_ref`

BIBLIO preserves traceability back to internal references and enriches existing entities before suggesting new ones.

### GHS

GHS converts external or fresh signals into evidence and currency.

It may produce:

- `freshness_signal`
- `evidence_item`
- `audit_log`

GHS enriches entities without replacing BIBLIO's stable editorial memory.

### SCHEMA

SCHEMA is the common contract. It does not decide content, write articles, crawl sources, resolve entities, or index knowledge. It only normalizes how knowledge moves.

### WRITY

WRITY consumes clean normalized context. It should not process massive memory, raw spreadsheets, or unordered fresh signals directly.

## Phase 1 Objects

- `source_packet`: raw input unit, such as a spreadsheet row, internal review, finished article, or fresh external signal.
- `source_ref`: verifiable reference to the origin of knowledge. It is represented by `schemas/source.schema.json` and can travel in `sources` or `source_refs`.
- `evidence_item`: extracted claim or observation backed by a source.
- `editorial_entity`: reusable poker niche entity. It is represented by `schemas/entities.schema.json` and can travel in `entities` or `editorial_entities`.
- `editorial_requirement`: requirement extracted from a spreadsheet or brief.
- `content_block`: normalized editorial block.
- `skeleton_decision`: structural decision made by SKULL.
- `freshness_signal`: current signal contributed by GHS.
- `reusable_note`: stable knowledge preserved by BIBLIO.
- `audit_log`: minimal trail of origin, date, confidence, and transformation.

## Minimal Audit Fields

Important data should be able to preserve:

- `source_id`
- `source_type`
- `original_location`
- `extraction_date`
- `transformation_step`
- `confidence`
- `stale_after`, when applicable
- `human_review_status`
- `notes`

## Compatibility

The existing `entities`, `relationships`, and `sources` arrays remain valid. Phase 1 adds optional aliases and arrays for planning objects, evidence, reusable notes, freshness, and audit logs.

## Out of Scope

FUTURE EDITORIAL MEMORY EXTRACTION:

- heavy NLP;
- crawlers;
- prompts;
- adapters;
- databases;
- frameworks;
- entity resolution;
- graph storage;
- massive processing of `Referencias/`;
- direct writing or indexing logic.
