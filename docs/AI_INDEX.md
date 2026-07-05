# AI Index - GT Editorial Schema

## Purpose

Lightweight navigation file for ChatGPT, Codex and future AI-assisted sessions.
Use this file to understand the role of `gt-editorial-schema` without scanning the whole repository.

## Repository role

`gt-editorial-schema` is the shared contract layer for the editorial ecosystem. It should define portable structures, naming conventions and exchange formats used by SEO-Articles, GHS-intelligence and future tools.

It should stay small, stable and implementation-agnostic.

## Relationship with other repos

- `SEO-Articles`: produces editorial workflows, SKULL/BIBLIO outputs and WRITY clean packages that should align with this schema.
- `GHS-intelligence`: returns entities, evidence, freshness signals and claim reviews that should map to this schema.
- Future tools: should consume or emit schema-compatible packages instead of redefining contracts locally.

## Read order for AI sessions

1. `AGENTS.md` if present
2. `README.md`
3. files under `docs/`
4. schema examples or fixtures only when needed for the task

## Schema responsibilities

This repo may define concepts such as:

- editorial sample metadata
- entity references
- claim clusters
- evidence items
- freshness signals
- audit logs
- clean WRITY packages
- BIBLIO note shapes
- GHS export shapes
- human review gates

## Design principles

- Keep schema fields explicit and boring.
- Prefer small composable objects over large implicit documents.
- Track source IDs and review status separately from prose.
- Treat legal, commercial, payments, KYC, safety, availability and regulatory claims as sensitive.
- Distinguish operator declarations from independent evidence.
- Use stable enums for claim states where possible.
- Preserve human review gates for risky topics.

## What this repo should not do

- Do not store private editorial source files.
- Do not contain full articles, raw spreadsheets or `.docx` sources.
- Do not duplicate GHS evidence gathering logic.
- Do not duplicate SEO-Articles workflow docs.
- Do not make WRITY write prose.
- Do not redefine project-specific decisions that belong in another repo.

## Naming notes

- Use `BIBLIO` as the visible tool/layer name.
- Use `biblio` only for filenames, IDs and machine-readable fields.
- Do not introduce `BiBLIO` in new docs.

## Recommended AI behavior

When updating this repo, propose schema-level changes only. If a change belongs to SEO-Articles, GHS-intelligence or WRITY behavior, document the interface here and move implementation details to the owning repo.

## Last updated

2026-07-05
