# Reviewing `specs/product/`

Instructions for agents reviewing the product specs ([`specs/product/product.md`](../../specs/product/product.md) and every file under [`specs/product/`](../../specs/product/)). Authoring rules for each file are in [`rules/README.md`](rules/README.md). Follow [`alignment.md`](alignment.md). The spec links that file and does not contain the rules. Read [`specs/vision.md`](../../specs/vision.md), [`specs/definition/definition.md`](../../specs/definition/definition.md), and [`specs/definition/quality.md`](../../specs/definition/quality.md) first. A review may cover the whole product set or named files; cross-spec checks always consider the whole set. Skip `_template.md` files. Run every check, then report a verdict.

## Aligned

Same sections and required content as the rules file for each spec in scope. File-level requirements in [`alignment.md`](alignment.md) hold.

### Completeness

- [ ] No `<!-- fill in -->` placeholders remain in formalized sections; unused template rows and sections there are deleted. A section that is still only a placeholder is not formalized ([`alignment.md`](alignment.md)).
- [ ] Each file links its authoring-rules file from [`rules/README.md`](rules/README.md). Those rules are not pasted into the spec. The authoring-rules link is not product content.
- [ ] The domain and product profile and index in `product.md`, and the alignment and topic coverage tables in `traceability.md`, are filled in.
- [ ] Every topic in the coverage table is covered, or marked N/A with a reason grounded in the domain profile or definition.
- [ ] Every unit spec is listed in the `product.md` index, and every indexed file exists.

### Self-contained detail

- [ ] Every rule, entity, and behavior is described in full, even for well-known domains.
- [ ] No spec depends on an external reference (named product, wiki, link) to be understood. The authoring-rules link does not count.
- [ ] Feature rules and product stories are precise enough that two readers reach the same outcome. A feature states the outcome of each edge case and simultaneous event.
- [ ] Every walkthrough in `scenarios/` can be resolved step by step from the other specs.
- [ ] Scenarios meet the minimum for the definition's spec depth in [`depth.md`](rules/depth.md).

### Shared language

- [ ] Each product term is defined once in `glossary.md` and used consistently; no synonyms.
- [ ] Each entity is defined once in its own file; other specs link instead of redefining.
- [ ] Parameter values appear only in `configuration.md`; other specs reference them by name.

### Internal consistency

- [ ] Every flow phase is reachable and has an exit, unless it ends the flow.
- [ ] Transitions state what carries over and what resets.
- [ ] Configuration modes and options referenced elsewhere exist.

### Element IDs

- [ ] Every section listed in [`ids.md`](rules/product/ids.md) gives each element an ID in the prescribed form, unique within its spec.
- [ ] Qualified IDs cited anywhere (e.g. `F-billing.R3`) exist.

### Product stories

Rules: [`stories.md`](rules/product/stories.md) and [`story.md`](rules/product/story.md).

- [ ] Every product spec with element IDs is a row in the `stories.md` index with core and coverage. The specs marked core include at least those [`depth.md`](rules/depth.md) names, and each coverage level meets the minimum for the definition's spec depth.
- [ ] Every spec whose coverage is not None has a story file at the mirrored path under `stories/`; no story file lacks a product spec.
- [ ] In each story file, every element ID and name-referenced item (fields, modes, options, tunables) is proven by at least one scenario, and the coverage table agrees with its scenarios' **Proves** lines.
- [ ] For each spec at Full coverage, every requirement in [`story-coverage.md`](rules/product/story-coverage.md) is met for each element kind.
- [ ] Knowledge scenarios state what the user can or cannot know, never how it is shown.
- [ ] Each scenario has a complete Given, one When (a user verb or product-defined event; chained only in walkthrough stories), and a Then with concrete values that match `configuration.md` or the Given.
- [ ] Each scenario is falsifiable: an implementation that breaks the element it proves would fail it. No subjective wording.
- [ ] No scenario asserts behavior absent from product, or mentions screens, inputs, or presentation.

### Alignment with vision and definition

- [ ] Every essential quality, in-scope item, and user objective is served by at least one spec, and `traceability.md` reflects this.
- [ ] Nothing serves only a vision non-goal or definition out-of-scope item.
- [ ] Outcomes and progression match the definition's user objectives.
- [ ] Where qualities conflict in product, the vision's tradeoff order is followed.
- [ ] Every spec states what it serves.
- [ ] When accessibility Applies in [`quality.md`](../../specs/definition/quality.md), a rule-changing assist or timing option is a row in `configuration.md`.
- [ ] Performance, latency, reliability, and observability targets appear only in [`quality.md`](../../specs/definition/quality.md).

### Domain and platform fit

- [ ] Adopted and rejected conventions are reflected in the relevant specs.
- [ ] Platform implications are reflected in flows, features, and configuration.
- [ ] Platforms appear only as product implications, never as hardware, input mapping, or APIs.

### Scope boundaries

- [ ] No UX design: no screens, menus, layouts, widgets, or input bindings. User actions are verbs. Interface structure belongs in [`specs/ux/`](../../specs/ux/ux.md).
- [ ] No technical design: no frameworks, code, data formats, or storage. A limit imposed by an architecture decision is stated in product terms and cites an ADR ID that exists in [`specs/adr/decisions/`](../../specs/adr/decisions/).

### Format

- [ ] Each file is under 500 words ([`specs/README.md`](../../specs/README.md)); oversized files are split by logical unit and linked.

## Imposed

- [ ] No two specs contradict each other.
- [ ] A rule outside feature rules and product stories is precise enough that two readers would resolve the same situation identically.

## Verdict

- **Pass**: every check passes.
- **Fail**: one or more checks fail.

Report back in this shape:

```markdown
**Product review: Pass | Fail**

Scope: <whole product | listed files>

Findings:
- <file>: aligned | imposed — <failed check> — <suggested fix>

Notes (optional): <non-blocking observations>
```

List only failed checks under Findings. Tag a check that cannot be judged without product-owner input with `needs clarification` as well. If the problem is in `vision.md` or the definition rather than product, say so. Refinement follows [`alignment.md`](alignment.md).
