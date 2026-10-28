# Authoring rules: product-story index

Read this before editing `specs/product/stories.md`. Do not copy these rules into the spec.

Also read [product.md](product.md), [ids.md](ids.md), [story-coverage.md](story-coverage.md), and [depth.md](../depth.md). A single story file follows [story.md](story.md).

Product stories are concrete, testable product behavior, written as Given/When/Then and traced to the product element IDs they prove. They cover product logic and rules. Interface behavior is a user story under `specs/ux/`.

## Rules for every story

- **Product logic only**: no screens, menus, inputs, buttons, feedback, animation, or sound. Interface behavior belongs in `specs/ux/stories.md`.
- **Traced**: every scenario names the element IDs it proves. A scenario must not assert behavior the product does not state. If the scenario is needed, change the product first.
- **Narrative**: each story opens with "As a \<user\>, I \<verb or situation\> so that \<goal\>". The goal comes from the product spec's purpose.
- **Given**: the complete starting situation (phase, entity state, participants, and configuration), so two testers would set up the same situation.
- **When**: exactly one trigger. Either a user verb, or a product event the spec defines (a deadline expires, a system job runs). Scenario-walkthrough stories may chain When/Then pairs in step order.
- **Then**: the resulting state changes, phase transitions, outcomes, or what the user can or cannot know, with concrete values. Add "And … is unchanged" wherever an unintended change is plausible.
- **Falsifiable**: name state fields and configuration parameters, each followed by a concrete value, such as `quota is MAX_QUOTA (10)`. Values match the defaults in `configuration.md` unless the Given sets them. Do not use subjective words such as "smoothly", "quickly", or "feels". An implementation that breaks the element would fail the scenario.
- **Shared language**: use glossary terms and entity and field names as defined.

## Coverage

Each product spec with element IDs is core or not, and has a coverage level of Full, Baseline, or None — reason. Spec depth sets the minimum for each, per [depth.md](../depth.md). Choose per spec.

- **Full**: every element ID and name-referenced item is proven as [story-coverage.md](story-coverage.md) requires.
- **Baseline**: every element ID and name-referenced item is proven by at least one scenario that shows its stated outcome.
- **None**: no story file.

The coverage table agrees with the scenarios' **Proves** lines. Sections without IDs are judged during review and acceptance, not by stories.

## Files

One story file per product spec that has element IDs and coverage other than None, at the same relative path under `specs/product/stories/`. `features/billing.md` → `stories/features/billing.md`. `demo.md` → `stories/demo.md`. Copy `stories/_template.md`.

A story that spans several specs lives in the file of the spec whose element it mainly proves. It cites the other specs' elements with qualified IDs.

`stories.md` is the index: one row per product spec that has element IDs, grouped as in the product index. Columns: the product spec link, core (yes or no), coverage (Full, Baseline, or None — reason), and the story file link (or "—" when None). If the index pushes the file past 500 words, move it to `stories/index.md` and leave a link.

Every indexed story file exists, and every story file has a product spec.
