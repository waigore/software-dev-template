---
name: create-poc
description: |-
  Build a proof of concept under pocs/<slug>/ after scope-poc passes:
  freer exploration of a technical or functional claim, not bound by specs.
  Use when the user asks for a PoC, prototype, or proof that a product approach
  is achievable (APIs, data shape, UX flow, tooling).

  Examples:
    - user: "Build a PoC of the core workflow" → scope-poc, then build a core PoC
    - user: "PoC task #21 passed review, build it" → scope check, then build
    - user: "Promote the auth PoC" → use reconcile-poc first
---

# Create PoC

Contract: [`docs/pocs.md`](../../../docs/pocs.md). README template: [`assets/poc-readme.md`](assets/poc-readme.md).

## Steps

### Scope

Run [`scope-poc`](../scope-poc/SKILL.md). Continue only when it passes. Do not restate its gate or scope rules.

### Build

1. **Start** per [`../_shared/change-pr.md`](../_shared/change-pr.md) (before editing). Branch `task/<n>-poc-<slug>` when a task owns the PoC, otherwise `chore/poc-<slug>`. Create `pocs/<slug>/`. Copy the template to `pocs/<slug>/README.md` and fill it. Issue may be none. Record the stack when the experiment needs one. Do not require a Stack ADR.
2. **Implement** only enough to answer the exploration question. Optional comments citing product/ADR IDs when drawn on. Do not touch code outside `pocs/<slug>/`. Record material spec findings as tasks (or repair in place), and product/interface bugs as defects — see [`docs/issues/requirements.md`](../../../docs/issues/requirements.md).
3. **Smoke run**: launch the PoC; record how to run it and what you saw vs the desired outcome. QA protocols per `specs/qa/` only if the user asks.
4. **PR** per [`../_shared/change-pr.md`](../_shared/change-pr.md) (after editing). Apply the PoC ask. Authority may be N/A (PoC) plus any ADRs or product cited. Skip `implement-project-issue` when no task owns the PoC.

## Rules

- Spec-first does **not** apply inside `pocs/`. Assumptions do not authorize main code.
- `docs/solid.md`, `docs/coding-conventions.md`, and structure continuity do not apply inside `pocs/`.
- Main code never imports from `pocs/`. Reusing PoC learning starts with [`reconcile-poc`](../reconcile-poc/SKILL.md), then [`promote-poc`](../promote-poc/SKILL.md) for a non-empty keep list.
- Do not grow scope during the build. A new need goes back through [`scope-poc`](../scope-poc/SKILL.md).
