# Authoring rules: QA procedures

Read this before editing `specs/qa/procedures.md` or a file split from it. Do not copy these rules into the spec.

Also read [qa.md](qa.md) and [tools.md](tools.md).

How the AI agent runs QA. Steps are agent-facing. Do not name frameworks or CI products. Do not duplicate the evidence artifact schema (that belongs in `evidence.md`). Do not list unit/integration seams (technical verification).

## When to run

Restate the hub gate: required at `status:pending-acceptance` when deliverables change runtime behavior; skip for spec-only, docs-only, or other non-runtime work.

## Select scope

- Read coverage mode from the hub and the set from [`coverage.md`](coverage.md).
- Map the issue to product story IDs and UX journey (or story) IDs in scope; intersect with that set.

## Prep

Require: build under test; Must tools from `tools.md` available; Situational tools ready when a selected protocol cites them; evidence folder opened under `docs/qa/evidence/` for this issue/run.

## Per protocol

Ordered steps the agent always follows: enter start position (including `DBG.3` when needed) → drive via user-facing controls and debug commands → observe via inspect, story-ID overlay, and telemetry → judge pass/fail against the cited product or UX story → write notes and logs into the evidence folder, and screenshots only when the protocol requires UI evidence. Product-level protocols judge product outcomes; UX-level protocols judge interface operation.

A headless run (no display) may complete those steps except screenshots. Missing screenshots are not a fail when the protocol does not require UI evidence. When a protocol requires UI evidence, a graphical run re-runs on the same build and writes the screenshots into its own run folder before acceptance.

## Outcomes

Default: any protocol fail for a product or interface reason blocks acceptance and may file a defect without screenshots. Record fail evidence and stop that protocol; remaining protocols may still run if useful, but acceptance must not pass while a required protocol has failed. When judgement is recorded and required screenshots are still waiting on a graphical re-run, stay on `status:pending-acceptance`. Non-blocking notes exist only when a protocol explicitly marks an observation as non-blocking.

## Splitting

If the file passes 500 words, move Per protocol detail to `procedures-run.md`. Leave a summary and a link, and update `qa.md`.
