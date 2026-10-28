# QA evidence

In-repo evidence from AI-agent QA runs. Schema and requirements: [`specs/qa/evidence.md`](../../../specs/qa/evidence.md). Gate and scope: [`specs/qa/qa.md`](../../../specs/qa/qa.md).

## Layout

`issue-<n>/<run-id>/` with at least:

- `manifest.md` — issue, build/session id, coverage mode, results table, paths
- `notes.md`
- `logs/`
- `screenshots/` — only when a protocol requires UI evidence

## When required

Only when acceptance deliverables change runtime product behavior. Spec-only and docs-only issues do not need a folder here.
