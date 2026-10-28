# Authoring rules: product story coverage

Read this before writing product stories. Do not copy this table into `specs/product/story-coverage.md` or into a story file. That file only links here.

Also read [stories.md](stories.md) and [ids.md](ids.md).

Every element is proven, not only mentioned.

This file is the Full coverage level. A spec at Baseline or None follows [depth.md](../depth.md) instead. The `stories.md` index records each spec's level.

## Every element

Every element ID and every name-referenced item (fields, modes, options, tunables) is proven by at least one scenario in the story file of the spec that defines it. Product tunables are proven in their owner spec's story file. Requirements below are cumulative: an element that is both conditional and numeric needs both sets of scenarios.

## Requirements by kind

| Element kind | Scenarios required |
|--------------|--------------------|
| Conditional element: a rule, action, transition, or adjustment that applies only when something holds | One where the condition holds and one where it does not |
| Numeric threshold | At the boundary and on each side of it |
| Edge case | One per edge case |
| Option or mode that changes an element | One under each choice that changes it |
| Product tunable (`CFG.<name>`) | In its owner spec's story file: behavior at the default and at both ends of its range |
| Mode (`CFG.<name>`) | One for each rule the mode changes |
| Entity property (`P`) | Its initial value from its parameter, and the effect it governs |
| Flow phase (`P`) | Each listed verb is available; each verb named as unavailable has no effect on product state |
| Walkthrough step | The stated outcome follows its trigger |

## Phrasing knowledge

State what the user can know, never how it is shown. Write "Then the user can know `<field>`" or "Then the user cannot know `<field>`". Never mention screens, indicators, or display.

## Not covered

Sections without IDs (purpose, motivation, user outcome intent, and similar) are not proven by stories. Review and acceptance judge them.
