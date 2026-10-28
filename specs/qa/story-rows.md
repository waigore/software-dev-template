# Story rows

Authoring rules: [`.agents/specs/rules/qa/story-rows.md`](../../.agents/specs/rules/qa/story-rows.md).

Story↔work map for product stories and UX journeys/stories. QA results live under [`docs/qa/evidence/`](../../docs/qa/evidence/). Issue routing: [`docs/issues/requirements.md`](../../docs/issues/requirements.md).

## Rows

| ID | Owner | Note |
|----|-------|------|
| <!-- fill in: product or UX story/journey ID --> | <!-- fill in: #n epic/task, or none --> | <!-- fill in: — if owned; durable reason if none --> |

## Owner rules

- **`#n`** — open epic or task that delivers the story.
- **`none`** — not delivered yet; Note holds a durable reason (e.g. out of wave, not in product). Link a **task** in Note only when material work is uncovered and needs an owner. Never require a `type:defect` for a `none` row.
- **Defects** — product/interface fails only; not planning owners for uncovered stories.
