# QA coverage

Authoring rules: [`.agents/specs/rules/qa/coverage.md`](../../.agents/specs/rules/qa/coverage.md).

## Mode

Declared on [`qa.md`](qa.md): `full` or `critical-only`.

| Mode | QA set |
|------|--------|
| `full` | Every product story and every UX journey (then intersected with issue scope in [`procedures.md`](procedures.md)) |
| `critical-only` | Only the Critical IDs table below (then intersected with issue scope) |

Prefer `full` for complex projects; `critical-only` for smaller ones with an explicit critical set.

## Critical IDs

| ID | Upstream story / journey ID | Why critical |
|----|-----------------------------|--------------|
| <!-- fill in: C1… when critical-only; or one row — / — / None — mode is full --> | <!-- fill in --> | <!-- fill in --> |

## Issue mapping

A required acceptance QA run covers the intersection of this coverage set and the product/UX IDs the issue's runtime deliverables can affect. See [`procedures.md`](procedures.md).

Delivery ownership (which epic/task owns a story, or `none` with a durable reason) lives in [`story-rows.md`](story-rows.md) — not in this file.
