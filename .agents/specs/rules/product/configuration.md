# Authoring rules: configuration

Read this before editing `specs/product/configuration.md` or a tunable file split from it. Do not copy these rules into the spec.

Also read [product.md](product.md) and [ids.md](ids.md). Stories for this file follow [story.md](story.md).

Everything that varies the product's rules without changing the product specs: modes and options chosen by the user or admin, and product tunables. This file is the single source of parameter values. Other specs reference parameters by name. Describe effects on rules, not menus or settings screens.

## Modes

Columns: mode, description, how it differs from the standard rules (or "Baseline"), and a link to the flow. Reference a mode by name, such as `CFG.trial`.

When [`demo.md`](demo.md) Offering is **offered**, include a demo mode (or options/tunables) whose differences cite `DEMO.L*` limitations. Do not invent demo caps only here—`demo.md` owns the product meaning.

## Options

Rule variants and assists the user or admin may choose.

When accessibility Applies in `specs/definition/quality.md` and names a rule-changing assist or timing option, that option is a row here.

Columns: option, choices, default, effect on rules, who chooses it and when (user or admin; before use or at any time), and when it is locked (or "Never").

## Product tunables

Balance or limit values a product owner adjusts. They are not user-selectable. Reference them by name, such as `CFG.MAX_QUOTA`. The owner spec's stories prove behavior at the default and at both ends of the range.

Columns: parameter, owner spec, default, range, unit (product units such as seats, days, or items), and effect.

## Dependencies and restrictions

IDs `K1`, `K2`, … per [ids.md](ids.md). Each entry is a combination that is not allowed, an option that depends on another, or an option that affects entitlements or progression.

## Splitting

If the file passes 500 words, move tunables to `configuration/<domain>.md` (for example `billing.md`, `limits.md`). Keep modes and options here, with links, and update owner specs.
