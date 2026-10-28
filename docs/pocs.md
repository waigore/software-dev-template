# Proofs of concept (PoCs)

A **PoC** is how a project explores a slice before that slice is formalized. It lives under `pocs/<slug>/`, apart from the main tree. It is **not** bound by `specs/` (it may draw on product specs, ADRs, or notes already decided). Main code never imports from `pocs/`.

Product **demo mode** is different: [`demo.md`](demo.md).

## Explore, then formalize

1. **Explore**: build the slice here. The README records the question, what is in and out, how to run it, and the stack when the experiment needs one.
2. **Iterate**: change the PoC freely on the local branch. Several PoCs may exist. Nothing here authorizes main-tree code. Ask before a PR ([Pull requests](#pull-requests)).
3. **Formalize**: a kept PoC enters the product through [`poc-promotion.md`](poc-promotion.md). Spec depth is the bar for that keep list.

## Request → track → build

1. **Request**: the user asks for a PoC, or an agent offers one when a slice is not yet formalized.
2. **Log**: write purpose, scope, and desired outcome in [`requirements/poc-requests.md`](requirements/poc-requests.md).
3. **File**: when agent-orc or a wave will own the PoC, create a task (or epic) whose body carries those fields. Dependents may use native **blocked-by** that issue only. An interactive session may build from a confirmed README without a task.
4. **Scope / build**: [`scope-poc`](../.agents/skills/scope-poc/SKILL.md), then [`create-poc`](../.agents/skills/create-poc/SKILL.md).

Already-specced main-tree work does not need a new PoC. Product behavior that is not in a formalized spec goes back to Explore.

## Pull requests

Commit on the local branch. Ask before any pull request for this PoC, including promotion ([`poc-promotion.md`](poc-promotion.md)). Open it only after the user agrees ([`pull-requests.md`](pull-requests.md)). A no leaves the branch unpushed, including when a task owns the work. Run `implement-project-issue` only after that PR exists.

## Types

| Type | Explores |
|------|----------|
| Core | Domain logic, state, APIs, data shape; no full UI. Debug overlay or CLI allowed. |
| Product | End-to-end slice with screens and flows |

Default to core unless the question is UI/flow or the user asks otherwise.

## Before building

[`scope-poc`](../.agents/skills/scope-poc/SKILL.md) applies this. Always: [`ensure-project-setup`](../.agents/skills/ensure-project-setup/SKILL.md) passed; purpose, scope, and desired outcome confirmed (README or task). Unfinished specs, a locked high-level stage, and an Accepted Stack ADR do not block. Record the stack in the README when the experiment needs one. The Stack ADR is written when the slice is formalized.

## What is relaxed

- [SOLID](solid.md), [coding conventions](coding-conventions.md), and structure continuity do not apply. `review-code` skips `pocs/`.
- Unit tests optional. Spec-first does **not** apply.
- QA protocols per `specs/qa/` optional, on request.

## Traceability (lightweight)

The PoC README records the exploration question, purpose/scope/outcome, optional product/ADR citations used, what was tried, and promotion status. Assumptions do not authorize main code.

## Verification

When a task owns the PoC, `verify-project-issue` checks it against the task’s purpose/outcome and README run instructions. No code review.
