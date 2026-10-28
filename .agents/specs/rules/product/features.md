# Authoring rules: feature

Read this before editing `specs/product/features/_template.md` or `specs/product/features/<name>.md`. Do not copy these rules into the spec.

Also read [product.md](product.md) and [ids.md](ids.md). Stories follow [story.md](story.md).

Copy the template to `features/<kebab-name>.md`, one file per capability or system. Do not fill the template in place.

A feature is a coherent set of product rules, such as auth, billing, search, notifications, or approval.

## Header

- **Kind**: capability, system, policy, or behavior.
- **Serves**: vision qualities and definition scope items.
- **Depends on**: links to other features, or "None".
- **Glossary terms**: links into `glossary.md`.

## Sections

- **Purpose**: the user decision or outcome this feature creates.
- **Rules**: precise and complete. Two readers must reach the same outcome for any situation. IDs `R1`, `R2`, …. Each rule states who or what acts, when, and what changes. State edge cases and simultaneous events. Parameter values are not written here.
- **Parameters**: values live in `configuration.md`. List each parameter this feature uses, by name, and its role in the rules.
- **State**: fields this feature reads or changes (entity properties or named product state). Columns: field, read or write, and when.
- **Interactions with other features**: `I1`, `I2`, …. Ordering, priority, or a conflict with another feature. Link it and cite its rule IDs.
- **Edge cases**: `X1`, `X2`, …. Columns: situation and outcome.
- **Configuration effects**: `D1`, `D2`, …. How a mode or option changes a rule. Cite the rule ID and link `configuration.md`.
- **User outcome intent**: what the user should achieve or understand when these rules fire. Intent only.
