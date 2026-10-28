# Glossary ownership

For [`audit-spec-terminology`](../SKILL.md). Sourced from [`.agents/specs/rules/`](../../../specs/rules/) glossary rules. Update when those rules change — see [README.md](README.md).

| Domain | Glossary path | Owns | Must not redefine |
|--------|---------------|------|-------------------|
| Product | `specs/product/glossary.md` (+ `glossary/*.md` splits) | Product terms; one-line pointers to entities/features | — |
| UX | `specs/ux/glossary.md` (+ splits) | UI terms (screens, controls, journeys, bindings) | Product domain terms |
| QA | `specs/qa/glossary.md` (+ splits) | Protocol, evidence, coverage, and story-row terms | Product and UX terms |
| Technical | `specs/technical/glossary.md` (+ splits) | Layers, modules, components, contracts, schemata, sequences | Product and UX terms |

## Skeleton rows (keep; do not treat as orphan)

| Domain | Required rows (from rules) |
|--------|----------------------------|
| UX | Actor, Binding, Control, Exception, Journey, Mockup, Region, Screen, UI action |
| QA | Coverage, Evidence, Protocol, Story row, Tool |
| Technical | Component, Contract, Diagram, Layer, Module, Schema, Sequence |

Product has no fixed skeleton list; entities/features get one-line entries pointing at their specs.

## Authoring conventions (all glossaries)

- One term per concept; no synonyms.
- One meaning per term in that glossary.
- Columns: term, one-sentence definition, where detailed (link or "here").
- Alphabetical rows; splits keep `glossary.md` as the index.
