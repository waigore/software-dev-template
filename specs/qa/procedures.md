# QA procedures

Authoring rules: [`.agents/specs/rules/qa/procedures.md`](../../.agents/specs/rules/qa/procedures.md).

## When to run

At `status:pending-acceptance` (`accept-project-issue`) when the issue's deliverables change runtime behavior. Skip for spec-only, docs-only, or other non-runtime deliverables. Gate detail: [`qa.md`](qa.md).

## Select scope

1. Read coverage **Mode** from the hub and the set from [`coverage.md`](coverage.md).
2. Map the issue to product story IDs and UX journey or story IDs it can affect.
3. Intersect (1) and (2).

## Prep

- Build under test is the one under acceptance.
- Must tools from [`tools.md`](tools.md) are available (`DBG.*`, `TEL.*`, both drive paths).
- Any Situational tool a selected protocol cites is available.
- Evidence folder exists under [`docs/qa/evidence/`](../../docs/qa/evidence/) for this issue/run.

## Per protocol

| Step | Action |
|------|--------|
| 1 | Enter the start position (use `DBG.3` when the protocol is not reachable from the default start). |
| 2 | Drive with user-facing controls and debug commands as the protocol requires. |
| 3 | Observe via `DBG.2`, `DBG.4`, and telemetry (`TEL.*`). |
| 4 | Judge pass/fail against the cited product story (product outcome) or UX story/journey (interface operation). |
| 5 | Write notes, logs, and `manifest.md` per [`evidence.md`](evidence.md). Write screenshots only when the protocol requires UI evidence. |

Use `DBG.1` when pausing aids a reliable observation. Use `SIT.*` only when the protocol requires them.

## Headless and graphical runs

A headless run (no display) may enter, drive, observe, and judge. It writes notes, logs, and `manifest.md`. Missing screenshots are not a fail when the protocol does not require UI evidence.

When a protocol requires UI evidence, a graphical run re-runs the protocols on the same build and writes the screenshots into its own run folder before acceptance. Its manifest names that same build id.

## Outcomes

- **Pass** — every required protocol for the issue passed, and any required UI screenshots from a graphical re-run of the same build are citable.
- **Fail** — any required protocol failed for a product or interface reason. Record notes and logs and stop that protocol. Other protocols may still run for signal, but acceptance must not pass while a required protocol has failed. This fail may file a defect without screenshots.
- **Waiting** — judgement is recorded and required screenshots are still waiting on a graphical re-run. Stay on `status:pending-acceptance`.
- **Notes** — non-blocking only if the protocol marks that observation as non-blocking; otherwise treat as fail.
