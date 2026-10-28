# Authoring rules: definition

Read this before editing `specs/definition/definition.md` or a section split out of it. Do not copy these rules into the spec.

Also read [vision.md](vision.md) and [depth.md](depth.md). Keep this document consistent with the vision.

The definition states what the product must be and the limits it is built within. Aim for one page. Technical details (architecture, frameworks, data formats, APIs) do not belong here. A technical constraint is allowed, and the stack choice is required (see **Stack**).

Replace every `<!-- fill in -->`. Delete unused rows.

## Scope

- **In scope**: features, modes, or capabilities the product will have.
- **Out of scope**: what is deliberately excluded. This complements the vision's non-goals.

Both lists are present. Items are concrete enough to decide whether a feature is in or out. No item is in both lists. In-scope items must not serve only a vision non-goal. Out-of-scope items must not remove something an essential quality depends on.

## Objectives

### User objectives

- **Goal**: what the user is trying to achieve.
- **Success / failure outcomes**: how a session or workflow ends successfully or not.
- **Progression**: how the user advances over time (onboarding, entitlements, maturity).

### Product objectives

What this project must achieve. Each objective is concrete, and completion is verifiable. Objectives support the elevator pitch and the user promise.

## Supported platforms

One row per platform: the platform, its primary input, and a priority of primary, secondary, or stretch. At least one platform is primary. Every primary platform is one the stack can reach.

## Stack

The stack shapes the whole product, so it is a product decision made here, not downstream.

- **Stack**: the primary runtime or framework the product is built on, or "Custom" for a bespoke stack. Then one line on why, grounded in the platforms, constraints, team, or vision qualities. No versions, plugins, or setup; the Stack ADR states those.
- **Implications**: one or two lines, in product terms, on what the choice fixes or limits, such as deployment model, platforms it can reach, or scale. Downstream specs rely on these without naming the stack products.

If the stack is not decided, both fields are TBD per [README.md](README.md). Until it is decided, no Stack ADR is Accepted.

## Constraints

Three subsections: product, technical, and market. Each has at least one constraint, or the word "None". One line per constraint, then why. Constraints do not contradict each other, the scope, or the vision's qualities and tradeoffs. A constraint imposed by an architecture decision cites its ID, such as `(ADR-0003)`, per [adr/adr.md](adr/adr.md).

## Spec depth

One of `prototype`, `small`, or `full`, then one line on why, grounded in the scope, product objectives, or constraints. [depth.md](depth.md) states what each level requires of the downstream specs.

## Quality expectations

Measurable targets live in `specs/definition/quality.md`. Link that file. Follow [quality.md](quality.md) when editing it.

## Splitting

If this file passes one page or 500 words, move the longest section to `specs/definition/<section>.md`. Leave a one-line summary and a link here, and add the new file to `specs/README.md`.
