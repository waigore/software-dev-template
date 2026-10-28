# Authoring rules: product-story file

Read this before editing a file under `specs/product/stories/`, including `stories/_template.md` when changing the form. Do not copy these rules into the story file.

Also read [stories.md](stories.md), [story-coverage.md](story-coverage.md), and [ids.md](ids.md).

Copy `specs/product/stories/_template.md` to the mirrored path of the product spec. One file per product spec. Do not fill the template in place.

## Header

- **Product spec**: link to the spec this file proves.
- **Spec key**: the key from [ids.md](ids.md), such as `F-billing`.
- **Glossary terms**: links into `glossary.md`.

## Coverage table

One row per element ID and name-referenced item the product spec defines, including tunables it owns. Columns are element, a short summary, and the scenario IDs that prove it (such as `PS1.1`, `PS1.2`). The table matches each scenario's **Proves** line. At Full coverage, meet every requirement in [story-coverage.md](story-coverage.md) for that element's kind. At Baseline, each row needs at least one scenario. The spec's coverage level is in the `stories.md` index.

## Stories

Number stories `PS1`, `PS2`, … and scenarios `PS1.1`, `PS1.2`, …. Each story uses the narrative line from [stories.md](stories.md). The user is the vision's audience. The goal comes from the product spec's purpose.

Each scenario has a **Proves** line (element IDs; qualify other specs' IDs, such as `R1`, `X2`, `DEMO.L1`) and one Given / When / Then block that follows [stories.md](stories.md). Add stories and scenarios until every coverage row is proven.

Knowledge scenarios state what the user can or cannot know. They never say how it is shown.
