# QA

Authoring rules: [`.agents/specs/rules/qa/qa.md`](../../.agents/specs/rules/qa/qa.md).

## Purpose

AI-agent QA proves the running build against product and UX stories. It is not a unit or integration test plan (see `specs/technical/verification.md`).

## Levels

| Level | Proves | Cites |
|-------|--------|-------|
| Product | Software behaves as specified for users | Product story / element IDs |
| UX | Actors can operate the interface as specified | UX story / journey IDs |

## Coverage

- **Mode**: <!-- fill in: full | critical-only -->
- **Critical IDs**: see [`coverage.md`](coverage.md)

## Gate

Required at `status:pending-acceptance` (`accept-project-issue`) when the issue's deliverables change runtime behavior. Not required for spec-only, docs-only, or other non-runtime deliverables.

## Evidence

Root: [`docs/qa/evidence/`](../../docs/qa/evidence/). Each required run records story IDs, pass/fail, notes, and logs. Screenshots only when the protocol requires UI evidence. Schema: [`evidence.md`](evidence.md).

## Architecture constraints

| Kind | Capability | QA need |
|------|------------|---------|
| Must | Debug UI | Agent can inspect and control product state while running protocols |
| Must | Telemetry events | Agent can correlate observations to story IDs and outcomes |
| Situational | Seed, replay, state dump — see [`tools.md`](tools.md) | When a protocol requires them |

ADRs and technical design (including verification seams) must satisfy Must rows. Situational rows apply only when a protocol needs them. Detail: [`tools.md`](tools.md).

## Traceability

[`traceability.md`](traceability.md).

## Index

Global specs: [`glossary.md`](glossary.md), [`ids.md`](ids.md), [`traceability.md`](traceability.md), [`coverage.md`](coverage.md), [`story-rows.md`](story-rows.md), [`tools.md`](tools.md), [`procedures.md`](procedures.md), [`evidence.md`](evidence.md).

- **Product protocols**: None yet — copy [`product/_template.md`](product/_template.md)
- **UX protocols**: None yet — copy [`ux/_template.md`](ux/_template.md)
