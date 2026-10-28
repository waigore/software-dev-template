# Authoring rules: QA

Read this before editing `specs/qa/qa.md`. Do not copy these rules into the spec.

Every other file under `specs/qa/` follows **Rules for every QA spec** below. Those rules files name this one under **Also read**.

QA proves the running build against product and UX stories. It is downstream of `specs/vision.md`, `specs/definition/definition.md`, `specs/definition/quality.md`, `specs/product/product.md`, and `specs/ux/ux.md`. Requirements here constrain ADRs and `specs/technical/` (especially verification seams and observability). If QA conflicts with upstream product or UX, change QA, or revise the upstream document first.

## Rules for every QA spec

- **Agent executor**: protocols are run by an AI agent, not a human session as the primary bar.
- **Two levels only**: Product protocols cite product story or element IDs; UX protocols cite UX story or journey IDs.
- **No technology dump**: name required capabilities (debug UI, telemetry events) in product terms. Frameworks, formats, and tool products belong in ADRs; seams and harness detail belong in `specs/technical/verification.md`.
- **Traceable**: every protocol and requirement states which product or UX IDs it proves. Hub and unit specs stay consistent with those IDs.
- **Evidence contract**: each required run records story IDs, pass/fail, notes, and logs under `docs/qa/evidence/`. Screenshots only when the protocol requires UI evidence.
- **Concise**: each Markdown file stays under 500 words. Split by logical unit and link.

## Purpose and levels

Fill in `qa.md`:

- **Purpose**: one short paragraph on what agent QA proves and what it does not (not unit/integration test plans; those stay in technical verification).
- **Levels** table: Product and UX rows — what each proves, and which upstream ID kinds it cites.

## Coverage

- **Mode**: `full` (every product story and every UX journey) or `critical-only` (only IDs marked critical). Declare Mode on the hub.
- **Critical IDs**: owned by [`coverage.md`](coverage.md). The hub links that file.

## Gate

State when QA is mandatory at acceptance: issues whose deliverables change runtime behavior. Spec-only, docs-only, or other non-runtime deliverables do not require QA. Cite `accept-project-issue` / `status:pending-acceptance` as the workflow gate.

## Evidence

State the root path `docs/qa/evidence/` and the required artifact kinds: story IDs, pass/fail, notes, and logs. Screenshots only when the protocol requires UI evidence.

## Architecture constraints

- **Must**: debug UI and telemetry events — each row states the QA need and that ADRs/technical must satisfy it.
- **Situational**: other capabilities (replay, seeds, state dump, and similar) — list as "when needed" with when they apply, or "None".

## Index

Keep the global-spec list (glossary, ids, traceability, coverage, story-rows, tools, procedures, evidence). For a protocol, copy `product/_template.md` or `ux/_template.md` to `<kebab-name>.md`, fill the copy, and add the link under Product protocols or UX protocols. Leave `_template.md` unchanged. When there are no protocols yet, write "None yet" and point at the template.

If the index pushes `qa.md` past 500 words, move the index to `specs/qa/index.md` and leave a link in `qa.md`.
