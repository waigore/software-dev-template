# Authoring rules: product element IDs

Read this before assigning or citing a product element ID. Do not copy these rules into `specs/product/ids.md` or into any other spec. That file only links here.

Also read [product.md](product.md).

Stable IDs let product stories, issues, and other specs name a behavior exactly.

## Format

- **Spec key**: the prefix from the table below plus the file name without extension. `features/billing.md` → `F-billing`. Global specs use the fixed key in the table.
- **Element ID**: a section letter plus a number, unique within its spec, such as `R3`. Use it bare inside the same spec. Elsewhere, qualify it with the spec key, such as `F-billing.R3`.
- **Story IDs**: `PS<n>` for a story and `PS<n>.<m>` for a scenario, qualified by the key of the product spec they prove, such as `F-billing.PS2.1`.

## Stability

- Never renumber or reuse an ID. A new element takes the next number after the highest ever used in that section.
- When an element is removed, delete it, leave the gap, and update every reference to it.
- When an element's meaning changes, keep its ID and update every story that proves it.
- Where order matters (priority, sequence), list order is authoritative, not the ID number.

## Keys and identified sections

| Spec | Key | Sections and their ID letters |
|------|-----|-------------------------------|
| `entities/` | `E-<name>` | Properties `P`, Lifecycle and states `S`, Interactions `I` |
| `features/` | `F-<name>` | Rules `R`, Interactions with other features `I`, Edge cases `X`, Configuration effects `D` |
| `flows/` | `FL-<name>` | Phases `P`, Transitions `T`, Entry and exit `N`, Interruptions `U` |
| `scenarios/` | `SC-<name>` | Walkthrough steps `W<walkthrough>.<step>`, such as `W2.3` |
| `configuration.md` | `CFG` | Modes, options, and product tunables by name, such as `CFG.trial`; Dependencies and restrictions `K` |
| `demo.md` | `DEMO` | Limitations `L`, Entry and exit `N` |

Sections not listed (purpose, motivation, user outcome intent, and similar) carry no IDs. They explain or motivate. Product stories do not prove them.

Every section in this table gives each element an ID in this form. A qualified ID cited anywhere must exist.
