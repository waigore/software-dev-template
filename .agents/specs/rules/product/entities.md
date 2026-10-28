# Authoring rules: entity

Read this before editing `specs/product/entities/_template.md` or `specs/product/entities/<name>.md`. Do not copy these rules into the spec.

Also read [product.md](product.md) and [ids.md](ids.md). Stories follow [story.md](story.md).

Copy the template to `entities/<kebab-name>.md`, one file per entity or tight entity group. Do not fill the template in place.

This file is the single definition of a domain object: a record, resource, document, account, or similar. Other specs link here. Give it a one-line glossary entry that points here.

## Header

- **Kind**: record, resource, document, account, or other.
- **Serves**: vision qualities and definition scope items.
- **Glossary terms**: links into `glossary.md`.

## Sections

- **Purpose**: why it exists, and the decision or outcome it creates.
- **Properties**: `P1`, `P2`, …. Values live in `configuration.md` when tunable. Reference them by name. Columns: property, what it governs, parameter name (or "—").
- **Lifecycle and states**: `S1`, `S2`, …. Columns: when the state is entered, behavior in the state, and which states it exits to.
- **Interactions**: `I1`, `I2`, …. Columns: what it interacts with (link the entity or feature), the trigger, and the precise outcome.
- **Availability and creation**: where and when instances appear, limits, and who may create or destroy them.
- **User outcome intent**: how it should come across to users. Intent only.
