# Spec authoring rules

Writing rules for `specs/`. One file per document type. This tree is the only copy of those rules.

Specs and `_template` files keep a section skeleton and an authoring-rules link. They do not contain the rules. Filling a spec must not change files under this directory.

Before creating or editing a file under `specs/`, read the rules file for its path in the table below, then every file named in that rules file's **Also read** line. Follow the [`author-spec`](../../skills/author-spec/SKILL.md) skill. How these rules relate to the review checklists is [alignment.md](../alignment.md).

Spec depth (`prototype`, `small`, or `full`) is set in `specs/definition/definition.md`. [depth.md](depth.md) states how it scales story coverage and diagrams for formalized elements. Screen and journey mockups (and Open Design binding) are required for every formalized screen and journey when the product has UI; see [ux/presentation.md](ux/presentation.md) and [`docs/ux-mockups.md`](../../../docs/ux-mockups.md). A rules file that says a requirement follows spec depth defers to it. At `prototype`, [depth.md](depth.md) may omit glossaries, element IDs, traceability tables, and story matrices for a formalized slice. That omission wins over a unit rules file that would otherwise require them. The slice still states the behavior.

## Undecided aspects (TBD)

This rule applies to every spec. When an aspect is not decided yet, write `TBD — <open question>` where the decision belongs: a field value, a table cell, a list item, or a sentence. Do not invent the decision, and do not leave `<!-- fill in -->` in its place.

- One open question per TBD, phrased so the product owner can answer it. Name the options when known: `TBD — REST or GraphQL?`.
- `TBD` is uppercase and reserved for this marker. A bare `TBD` with no question fails Spec lint.
- Keep the section skeleton. A whole section may be a single TBD line.
- A downstream spec does not build on a TBD. An aspect that depends on one is TBD too, and its question links the upstream spec.
- Code does not implement a TBD aspect.
- `<!-- fill in -->` means not formalized. Leave it until that section is formalized. TBD means captured but undecided. `N/A — reason` means it does not apply.

Resolve TBDs with the `audit-spec-tbd` skill, then `author-spec`.

## Path table

Match the most specific path. A file split out from a spec uses the rules file of the spec it came from. For example, `specs/definition/quality/performance.md` uses [quality.md](quality.md), and `specs/product/glossary/auth.md` uses [product/glossary.md](product/glossary.md).

Do not paste these rules into a spec. Do not edit a `_template` file to hold one project's content. Copy the template, then fill the copy.

| Path | Rules |
|------|-------|
| `specs/vision.md` | [vision.md](vision.md) |
| `specs/definition/definition.md` | [definition.md](definition.md) |
| `specs/definition/quality.md` | [quality.md](quality.md) |
| `specs/product/product.md` | [product/product.md](product/product.md) |
| `specs/product/glossary.md` | [product/glossary.md](product/glossary.md) |
| `specs/product/traceability.md` | [product/traceability.md](product/traceability.md) |
| `specs/product/ids.md` | [product/ids.md](product/ids.md) |
| `specs/product/stories.md` | [product/stories.md](product/stories.md) |
| `specs/product/stories/` | [product/story.md](product/story.md) |
| `specs/product/story-coverage.md` | [product/story-coverage.md](product/story-coverage.md) |
| `specs/product/configuration.md` | [product/configuration.md](product/configuration.md) |
| `specs/product/demo.md` | [product/demo.md](product/demo.md) |
| `specs/product/entities/` | [product/entities.md](product/entities.md) |
| `specs/product/features/` | [product/features.md](product/features.md) |
| `specs/product/flows/` | [product/flows.md](product/flows.md) |
| `specs/product/scenarios/` | [product/scenarios.md](product/scenarios.md) |
| `specs/ux/ux.md` | [ux/ux.md](ux/ux.md) |
| `specs/ux/glossary.md` | [ux/glossary.md](ux/glossary.md) |
| `specs/ux/traceability.md` | [ux/traceability.md](ux/traceability.md) |
| `specs/ux/ids.md` | [ux/ids.md](ux/ids.md) |
| `specs/ux/stories.md` | [ux/stories.md](ux/stories.md) |
| `specs/ux/stories/` | [ux/story.md](ux/story.md) |
| `specs/ux/story-coverage.md` | [ux/story-coverage.md](ux/story-coverage.md) |
| `specs/ux/navigation.md` | [ux/navigation.md](ux/navigation.md) |
| `specs/ux/exceptions.md` | [ux/exceptions.md](ux/exceptions.md) |
| `specs/ux/controls.md` | [ux/controls.md](ux/controls.md) |
| `specs/ux/presentation.md` | [ux/presentation.md](ux/presentation.md) |
| `specs/ux/actors/` | [ux/actors.md](ux/actors.md) |
| `specs/ux/screens/` | [ux/screens.md](ux/screens.md) |
| `specs/ux/journeys/` | [ux/journeys.md](ux/journeys.md) |
| `specs/ux/mockups/README.md` | [ux/presentation.md](ux/presentation.md) |
| `specs/ux/mockups/catalog.md` | [ux/mockup-catalog.md](ux/mockup-catalog.md) |
| `specs/ux/mockups/screens/` | [ux/screen-mockup.md](ux/screen-mockup.md) |
| `specs/ux/mockups/journeys/` | [ux/journey-mockup.md](ux/journey-mockup.md) |
| `specs/qa/qa.md` | [qa/qa.md](qa/qa.md) |
| `specs/qa/glossary.md` | [qa/glossary.md](qa/glossary.md) |
| `specs/qa/ids.md` | [qa/ids.md](qa/ids.md) |
| `specs/qa/traceability.md` | [qa/traceability.md](qa/traceability.md) |
| `specs/qa/coverage.md` | [qa/coverage.md](qa/coverage.md) |
| `specs/qa/story-rows.md` | [qa/story-rows.md](qa/story-rows.md) |
| `specs/qa/tools.md` | [qa/tools.md](qa/tools.md) |
| `specs/qa/procedures.md` | [qa/procedures.md](qa/procedures.md) |
| `specs/qa/evidence.md` | [qa/evidence.md](qa/evidence.md) |
| `specs/qa/product/` | [qa/protocol.md](qa/protocol.md) |
| `specs/qa/ux/` | [qa/protocol.md](qa/protocol.md) |
| `specs/adr/adr.md` | [adr/adr.md](adr/adr.md) |
| `specs/adr/traceability.md` | [adr/traceability.md](adr/traceability.md) |
| `specs/adr/decisions/` | [adr/decision.md](adr/decision.md) |
| `specs/adr/archive/README.md` | [adr/adr.md](adr/adr.md) |
| `specs/adr/archive/` | [adr/decision.md](adr/decision.md) |
| `specs/technical/technical.md` | [technical/technical.md](technical/technical.md) |
| `specs/technical/glossary.md` | [technical/glossary.md](technical/glossary.md) |
| `specs/technical/traceability.md` | [technical/traceability.md](technical/traceability.md) |
| `specs/technical/ids.md` | [technical/ids.md](technical/ids.md) |
| `specs/technical/layers.md` | [technical/layers.md](technical/layers.md) |
| `specs/technical/modules.md` | [technical/modules.md](technical/modules.md) |
| `specs/technical/modules/` | [technical/modules.md](technical/modules.md) |
| `specs/technical/components/` | [technical/components.md](technical/components.md) |
| `specs/technical/contracts/` | [technical/contracts.md](technical/contracts.md) |
| `specs/technical/schemata/` | [technical/schemata.md](technical/schemata.md) |
| `specs/technical/sequences/` | [technical/sequences.md](technical/sequences.md) |
| `specs/technical/failures.md` | [technical/failures.md](technical/failures.md) |
| `specs/technical/concurrency.md` | [technical/concurrency.md](technical/concurrency.md) |
| `specs/technical/persistence.md` | [technical/persistence.md](technical/persistence.md) |
| `specs/technical/configuration.md` | [technical/configuration.md](technical/configuration.md) |
| `specs/technical/verification.md` | [technical/verification.md](technical/verification.md) |
| `specs/technical/_templates/` | matching optional rules file (e.g. [technical/failures.md](technical/failures.md)) |
| `specs/technical/diagrams/` | [technical/diagrams.md](technical/diagrams.md) |

Review checklists stay beside this tree, in [`.agents/specs/`](../). They judge specs. They are not pasted into `specs/` either.
