# Reviewing `specs/qa/`

Instructions for agents reviewing the QA specs ([`specs/qa/qa.md`](../../specs/qa/qa.md) and every file under [`specs/qa/`](../../specs/qa/)). Authoring rules for each file are in [`rules/README.md`](rules/README.md). Follow [`alignment.md`](alignment.md). The spec links that file and does not contain the rules. Read [`specs/vision.md`](../../specs/vision.md), [`specs/definition/definition.md`](../../specs/definition/definition.md), [`specs/definition/quality.md`](../../specs/definition/quality.md), [`specs/product/product.md`](../../specs/product/product.md), and [`specs/ux/ux.md`](../../specs/ux/ux.md) first. When a QA file cites a product or UX ID, confirm that ID exists. A review may cover the whole set or named files. Skip `_template.md`. Run every check, then report a verdict.

## Aligned

Same sections and required content as the rules file for each spec in scope. File-level requirements in [`alignment.md`](alignment.md) hold.

### Completeness

- [ ] No `<!-- fill in -->` placeholders remain in formalized Markdown. Unused rows the rules say to delete are deleted there. A section that is still only a placeholder is not formalized ([`alignment.md`](alignment.md)).
- [ ] Each Markdown file links its authoring-rules file from [`rules/README.md`](rules/README.md). Those rules are not pasted into the spec.
- [ ] Purpose, levels, coverage, gate, evidence, architecture constraints, and index in `qa.md` are filled per [qa.md](rules/qa/qa.md).
- [ ] Coverage mode on the hub is `full` or `critical-only`. Critical IDs follow [coverage.md](rules/qa/coverage.md).
- [ ] Global specs (glossary, ids, traceability, coverage, story-rows, tools, procedures, evidence) exist and are linked from the hub.
- [ ] When `story-rows.md` exists: one row per in-scope product/UX story ID; Owner is an open epic/task `#n` or `none` with a durable reason; `none` must not require a linked `type:defect`; defects are not planning owners ([story-rows.md](rules/qa/story-rows.md)).
- [ ] Every protocol file under `product/` or `ux/` (except `_template.md`) is listed in the hub index, and every indexed file exists. "None yet" is used when there are no protocols yet.

### Scope boundaries

- [ ] Executor is an AI agent. Protocols do not assume a human session as the primary bar.
- [ ] Only Product and UX levels exist.
- [ ] Gate requires QA at pending-acceptance only when deliverables change runtime behavior; excludes spec-only and docs-only work.
- [ ] Evidence root is `docs/qa/evidence/` with story IDs, pass/fail, notes, and logs. Screenshots only when the protocol requires UI evidence.
- [ ] Must architecture constraints include debug UI and telemetry events. Named frameworks and tool products are not introduced here (ADRs own those).
- [ ] Not a substitute for `specs/technical/verification.md` unit/integration seams.
- [ ] When `tools.md` exists: Drive is both user-facing and debug; Must debug rows include pause/resume, inspect, jump, story-ID overlay; telemetry minimum fields match [tools.md](rules/qa/tools.md); Situational rows state when they apply; no product/tool names.
- [ ] When `procedures.md` exists: When to run matches the hub gate; scope selection uses hub coverage mode; prep requires Must tools and an evidence folder; per-protocol steps cover enter, drive, observe, judge, capture; screenshots only when the protocol requires UI evidence; product or interface fails block acceptance by default; no framework/CI product names.
- [ ] When `evidence.md` exists: root and `issue-<n>/<run-id>/` layout; required artifacts include story IDs, pass/fail, notes, logs, and `manifest.md`; screenshots follow [evidence.md](rules/qa/evidence.md); retention until accept outcome; skip when QA not required; no sink/format product names.
- [ ] Glossary terms match [glossary.md](rules/qa/glossary.md); IDs match [ids.md](rules/qa/ids.md).
- [ ] Each filled protocol matches [protocol.md](rules/qa/protocol.md): level, cites, tools, steps, pass/fail, evidence.

### Traceability

- [ ] Cited product and UX IDs exist when protocols or critical lists name them.
- [ ] Nothing serves only a vision non-goal or a definition out-of-scope item.
- [ ] `traceability.md` alignment and topic coverage tables are filled per [traceability.md](rules/qa/traceability.md).

## Imposed

- [ ] Coverage mode matches project scale: complex projects use `full`; smaller projects may use `critical-only` with an explicit critical set.
- [ ] Must constraints are strong enough that ADRs and technical design can be judged for support (or an explicit gap is noted for a later ADR/technical session).

## Report

Verdict: **Pass** or **Fail**. List each failed check with `aligned` or `imposed`, and `needs clarification` when product-owner input is required. Do not invent sections or required fields.
