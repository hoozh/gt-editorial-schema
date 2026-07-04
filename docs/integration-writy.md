# Integration: WRITY

WRITY is the writing side of the contract.

## Responsibility

WRITY should use trusted entities, relationships, and taxonomy values to write with better context, consistency, and internal linking.

## Usage

WRITY can consume entities from BiBLIO or from a direct `export_bundle` when needed.

Useful fields for writing:

- `name`
- `aliases`
- `summary`
- `type`
- `relationships`
- `source_ids`
- taxonomy values such as `article_types`, `block_types`, and `keyword_types`

## Guidance

- Treat `summary` as factual context, not final copy.
- Prefer canonical IDs for internal linking.
- Use aliases for natural mentions, not for creating duplicate entities.
- Keep prompts, tone rules, and article generation logic inside WRITY.
