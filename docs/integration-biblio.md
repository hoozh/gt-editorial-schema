# Integration: BiBLIO

BiBLIO is the knowledge indexing side of the contract.

## Responsibility

BiBLIO should import export bundles, index entities and relationships, and make them searchable for editorial planning, research, and retrieval.

## Import expectations

BiBLIO should treat this repo as the contract for incoming objects:

- Validate bundle structure before indexing.
- Preserve canonical entity IDs.
- Preserve source links and relationship confidence.
- Keep local annotations separate from the shared contract.

## Guidance

- Use `entity.type` to decide collection, namespace, or display grouping.
- Use `relationship.type` to build knowledge graph edges.
- Use `source_ids` to surface provenance.
- Do not require WRITY-specific writing fields in the shared entity model.
