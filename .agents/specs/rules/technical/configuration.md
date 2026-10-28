# Authoring rules: technical configuration

Read this before editing `specs/technical/_templates/configuration.md` or `specs/technical/configuration.md`. Do not copy these rules into the spec.

Also read [technical.md](technical.md) and [ids.md](ids.md).

Optional. Create only when config sources, data-driven tables, or binding into components are non-trivial. Copy `_templates/configuration.md` to `configuration.md`; do not fill the template in place.

Product parameter *values and meaning* stay in `specs/product/configuration.md`. This file states how those params (and related tables) are sourced and bound in code.

## Header

- **Serves**, **Informed by**, **ADRs**: as in [components.md](components.md).
- **Product config**: link to `specs/product/configuration.md`.

## Sections

- **Sources**: `S1`, `S2`, …. Where config lives, format or shape, when loaded, owner.
- **Tables and tunables**: `T1`, `T2`, …. Name, product param link, type, default or range as code sees it (cite product; do not invent new product params).
- **Binding**: `B1`, `B2`, …. Which component reads which source or table, and failure if missing.
- **Diagram**: optional; add when source → consumer flow is hard to follow in prose.
