# Authoring rules: QA evidence

Read this before editing `specs/qa/evidence.md` or a file split from it. Do not copy these rules into the spec.

Also read [qa.md](qa.md), [tools.md](tools.md), and [procedures.md](procedures.md). Keep [`docs/qa/evidence/README.md`](../../../../docs/qa/evidence/README.md) consistent with this schema (process layout, not a second product spec).

What a required AI-agent QA run must leave in the repo so `accept-project-issue` can cite it. No framework, log-sink, or image-format product names.

## Root and layout

- Root path: `docs/qa/evidence/`.
- One folder per issue/run: `issue-<n>/<run-id>/` (run-id is a date or opaque id).
- When the hub gate says QA is not required, no evidence folder is required.

## Required artifacts

Each required run includes: story IDs covered; pass/fail per story or protocol; notes; logs. Screenshots only when the protocol requires UI evidence. Name the files or subfolders the agent must write (relative to the run folder).

## Manifest

Require `manifest.md` in the run folder. It lists: issue number, build or session id, coverage mode, a table of story (or protocol) ID → pass/fail, and relative paths to notes, logs, and screenshots when required. A run waiting on UI screenshots marks those paths as waiting on a graphical run. Do not require JSON unless the project later adds it via ADR.

## Screenshots, logs, notes

- **Screenshots**: only when the protocol requires UI evidence. Then at least one image per failed protocol; for a pass, at least one image showing the judged state. Images come from a graphical run that re-runs the protocols on the same build the judgement used, stored under `screenshots/` in that run's folder.
- **Headless run**: may judge and record pass/fail, notes, and logs with no display. It may omit screenshots. That omission is not a protocol fail when UI evidence is not required. When UI evidence is required, leave the issue on `status:pending-acceptance` until the graphical screenshots exist. A product or interface fail may still file a defect without screenshots.
- **Logs**: excerpt covering the judged window so `TEL.*` fields can be correlated; path listed in the manifest.
- **Notes**: what was judged; blockers; non-blocking marks only when the protocol allows.

## Retention

Evidence for a required run stays in-repo at least until the accept outcome for that issue is recorded. Do not delete or empty the run folder before that.

## Splitting

If the file passes 500 words, move the manifest field list to `evidence-manifest.md`. Leave a summary and a link, and update `qa.md`.
