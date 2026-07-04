# Philosophy

This repository is intentionally boring.

The contract exists so separate editorial systems can share meaning without sharing implementation. A brand, event, person, topic, relationship, or source should mean the same thing when it moves from GHS-intelligence to BiBLIO or WRITY.

## Principles

- Keep the schema portable and readable.
- Prefer clear IDs and small objects over clever abstractions.
- Store facts and relationships, not generated prose.
- Keep confidence and provenance close to the data.
- Let each product decide how to process, rank, enrich, or display the data.

## Boundaries

This repo should not contain:

- Crawlers.
- AI prompts.
- ranking logic.
- database migrations.
- product-specific adapters.
- heavy validation frameworks.

It should contain the shared contract those systems can trust.
