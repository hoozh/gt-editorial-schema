# Editorial Knowledge Graph

This document is the architectural reference for evolving `gt-editorial-schema` toward an Editorial Knowledge Graph.

The goal is not to implement a graph in this repository. The goal is to keep a small, modular, token-efficient shared contract that lets multiple editorial systems accumulate reusable knowledge over years.

## Vision

The ecosystem should treat entities as its primary asset.

Brands, people, events, products, markets, topics, organizations, offers, documents, reviews, articles, and news items may all appear in editorial workflows. The durable memory of the ecosystem, however, should be organized around canonical entities and the relationships between them.

Documents, spreadsheets, reviews, articles, and news are evidence. They help prove, update, explain, or challenge knowledge, but they are not the main memory layer.

The shared contract should therefore remain centered on:

- canonical entities with stable IDs;
- relationships that can be enriched over time;
- source references that preserve evidence and provenance;
- portable taxonomy values;
- small objects that can move between projects without bringing application logic with them.

## Ecosystem Roles

GHS discovers and enriches fresh knowledge. It should identify candidate entities, relationships, and evidence from external or recent sources, then export structured knowledge using this contract.

BiBLIO preserves and organizes editorial memory. It should import structured bundles, retain canonical IDs, index entities and relationships, and keep long-term knowledge reusable for planning, research, retrieval, and future writing.

SKULL interprets spreadsheets and generates skeletons aligned to the shared schema. It should translate operational inputs into structured editorial planning without becoming the canonical memory itself.

WRITY consumes only knowledge that is already structured. It should use trusted entities, relationships, taxonomy values, and source-backed context to write with consistency, but it should not create the canonical memory layer.

## Core Philosophy

- Entities are the primary asset of the ecosystem.
- Each entity should have a canonical identity and stable IDs.
- Every project should enrich existing entities before creating new ones.
- Knowledge is organized around canonical entities and their relationships.
- Relationships are as important as entities and must be able to accumulate evidence, confidence, and context over time.
- Documents, spreadsheets, reviews, articles, and news are evidence, not the main memory layer.
- The objective is to accumulate reusable knowledge for years, not only produce individual articles.
- The contract should be reusable across editorial niches, not designed only for poker.
- The schema should remain lightweight, modular, and token-efficient.

## Contract Boundaries

`gt-editorial-schema` should define shared shapes, taxonomies, examples, and architectural guidance. It should not contain crawlers, ranking logic, prompts, databases, graph traversal, entity-resolution logic, or project-specific adapters.

The current contract can support graph-shaped knowledge through:

- `schemas/entities.schema.json` for canonical editorial entities;
- `schemas/relationships.schema.json` for entity-to-entity relationships;
- `schemas/source.schema.json` for evidence and provenance;
- `schemas/export_bundle.schema.json` for portable exchange between systems;
- `taxonomy/` values for stable shared vocabulary.

Future changes should prefer additive optional fields and taxonomy extensions. Required fields, renamed IDs, graph-specific storage assumptions, or niche-specific fields should be avoided unless there is a clear cross-project need.

## Canonical Identity

Canonical identity is the foundation of the future graph.

An entity ID should remain stable even when the entity gains aliases, updated summaries, new sources, new relationships, or richer attributes. Aliases should improve recall and writing quality, but they should not create duplicate entities by default.

Before any project creates a new entity, it should try to match and enrich an existing canonical entity. When certainty is low, the project should preserve evidence and confidence rather than inventing a permanent identity too early.

## Evidence Model

Evidence should support knowledge without becoming the knowledge layer.

Sources, spreadsheets, articles, reviews, and news items can justify fields on entities and relationships. They may also reveal conflicts or freshness gaps. The canonical entity and relationship objects should remain the reusable memory, while sources remain provenance.

This distinction keeps WRITY from depending on raw documents, lets BiBLIO organize durable memory, and allows GHS to keep discovering fresh evidence without rewriting the whole ecosystem.

## Relationship Model

Relationships must be first-class knowledge objects.

They should support stable IDs, typed relationship values, source references, confidence, notes, and future enrichment. A relationship can become more useful over time as new evidence arrives, confidence changes, or the ecosystem learns more about context.

The contract should avoid treating relationships as simple inline text on entities. Inline summaries are useful for humans and writers, but the reusable graph depends on portable relationship objects.

## FUTURE ENTITY GRAPH

The following capabilities are important, but they are intentionally not part of the current contract:

- Entity Resolution: future systems should resolve aliases, duplicates, ambiguous names, conflicting sources, and candidate matches into canonical entities.
- Editorial Score: prioritization and ranking of entities, relationships, or opportunities should be handled by future ecosystem logic, not by this contract today.
- Graph Storage: the contract should not choose a database, index, traversal engine, or graph implementation.
- Relationship Enrichment: future schema versions may add optional fields for temporal validity, relationship attributes, relationship summaries, evidence strength, or review state.
- Entity Lineage: future schema versions may track merges, splits, redirects, deprecated IDs, or canonical replacement IDs.
- Evidence Granularity: future schema versions may reference exact document ranges, spreadsheet cells, article sections, extracted claims, or citation snippets.
- Freshness and Decay: future systems may track when knowledge becomes stale, expires, or needs revalidation.
- Cross-Niche Expansion: future taxonomy values should support new editorial verticals without renaming existing IDs.

## Decision Rules

When evolving this contract:

1. Preserve compatibility before adding expressiveness.
2. Prefer optional fields over required fields.
3. Prefer reusable editorial concepts over niche-specific concepts.
4. Keep provenance close to entities and relationships.
5. Keep application logic outside this repository.
6. Enrich existing entities before creating new ones.
7. Treat relationships as durable knowledge, not secondary metadata.
8. Document future graph ideas under `FUTURE ENTITY GRAPH` until the contract is ready for them.

