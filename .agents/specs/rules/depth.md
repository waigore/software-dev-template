# Authoring rules: spec depth

Read this before editing the **Spec depth** section of `specs/definition/definition.md`, and wherever another rules file says a requirement follows spec depth. Do not copy these rules into a spec.

Spec depth sets how much proof and how many visual artifacts a formalized slice carries. It applies to formalized elements only. A section or file that is still only `<!-- fill in -->` placeholders is not formalized; leave those placeholders. At `small` and `full`, a formalized spec stays self-contained, precise, traced, and identified. At `prototype`, a formalized rule may name a convention and state only the deltas, and one scenario is the proof.

## Levels

- **prototype**: a spike, a vertical slice, or a test of the core idea.
- **small**: a complete product of modest scope, such as one core flow, a handful of features, and a few screens.
- **full**: everything the rules require. Use it when unsure.

## Same for every formalized element

The N/A rules in each rules file apply at every depth. An Accepted ADR is required for each stack choice that main-tree code uses. Write that ADR when the slice is formalized, not before a PoC.

Glossaries, element IDs, and traceability tables apply to formalized elements at `small` and `full`. At `prototype` they are not required. Do not add a story matrix at `prototype`.

## Core specs

Each story index (`specs/product/stories.md`, `specs/ux/stories.md`) marks every formalized spec with element IDs as core or not. Core is judged among formalized specs. Unformalized flows and screens are not core yet. Core is what a user needs to start a session, complete the primary flow, and reach a success or failure outcome. When one of these is formalized, mark it core:

- **Product**: the features the primary flow uses, the flows that contain it, and configuration modes those features depend on.
- **UX**: `navigation.md`, `controls.md`, the screens on the path from launch into the primary flow and on to the result, the journeys that walk that path, and every screen those journeys reach.

Mark any other spec core case by case, when a defect there would be costly or hard to notice, such as auth, billing, or hidden information.

## Story coverage

Each formalized spec in a story index has one coverage level. An unfilled story index is not formalized:

- **Full**: every requirement in that layer's `story-coverage.md` rules.
- **Baseline**: every element ID and named item in the spec is proven by at least one scenario that shows its stated outcome. The requirements-by-kind table does not apply. Add scenarios case by case, such as a boundary or edge case the primary flow depends on.
- **None — reason**: no story file. The reason names the depth and why the spec is not proven, such as "not core, cosmetic only".

| Depth | Core spec | Other spec |
|-------|-----------|------------|
| full | Full | Full |
| small | Full | Baseline, or None — reason |
| prototype | None — reason | None — reason |

The table sets the minimum. Any spec may take a higher level. Choose per spec. At prototype, the reason cites spec depth, and the formalized product states one scenario for the slice. Story files are optional.

## Visual artifacts

| Artifact | full | small | prototype |
|----------|------|-------|-----------|
| Screen mockups | Every formalized screen, per platform | Every formalized screen; primary platforms only when multi-platform | Every formalized screen; primary platforms only when multi-platform |
| Journey mockups | Every formalized journey | Every formalized journey | Every formalized journey |
| Open Design binding | Required for those mockups | Required for those mockups | Required for those mockups |

Screen and journey mockups, and the Open Design binding that produces them, are required for every formalized screen and journey when the product has UI. They are not required for screens that have not been kept. Catalog approval gates that UI ([`docs/ux-mockups.md`](../../../docs/ux-mockups.md)). An artifact in the table is required only when its owning spec is formalized.

The Mockups topic in `specs/ux/traceability.md`, once that file is formalized, is never N/A merely because of spec depth. It may be N/A when the formalized slice has no screens or journeys.

## Other effects

- **Scenarios** (`specs/product/scenarios/`): at full, the scenario rules apply unchanged. At small, at least one scenario walks the primary flow to a success or failure outcome, and more are optional. At prototype, the Scenarios topic may be N/A citing spec depth.
- **Quality** (`specs/definition/quality.md`): at prototype, an N/A reason may cite spec depth for every category except performance.

## Changing depth

Raising the depth raises the minimums for every formalized spec. Backfill stories and artifacts before the next spec review passes. Lowering it removes nothing by itself. Keep existing stories and artifacts current, or delete them along with their index entries.
