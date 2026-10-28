# QA evidence

Authoring rules: [`.agents/specs/rules/qa/evidence.md`](../../.agents/specs/rules/qa/evidence.md).

## Root and layout

- **Root**: [`docs/qa/evidence/`](../../docs/qa/evidence/)
- **Run folder**: `issue-<n>/<run-id>/` (date or opaque run id)
- **Skip**: when [`qa.md`](qa.md) says QA is not required, no folder is required

## Required artifacts

| Artifact | Requirement |
|----------|-------------|
| Story IDs | Every product/UX story (or protocol) in the run's scope |
| Pass / fail | One outcome per story or protocol |
| Screenshots | Only when the protocol requires UI evidence |
| Notes | Judgement text for the run |
| Logs | Session excerpt for the judged window |
| `manifest.md` | Index of the above |

## Manifest (`manifest.md`)

| Field | Content |
|-------|---------|
| Issue | GitHub issue number |
| Build / session id | Matches `TEL.3` where possible |
| Coverage mode | `full` or `critical-only` from the hub |
| Results | Table: story or protocol ID → pass / fail |
| Paths | Relative paths to notes, logs, and screenshots when required. Mark waiting paths when UI evidence is still pending |

## Screenshots, logs, notes

- **Screenshots**: Only when the protocol requires UI evidence. ≥1 image per **failed** protocol; for each **pass**, ≥1 image of the judged state. Images come from a **graphical run** that re-runs the protocols on the same build the judgement used. Store them under `screenshots/` in that graphical run's folder.
- **Headless run**: May judge and record pass/fail, notes, and logs with no display. Omit `screenshots/` unless UI evidence is required (then mark paths waiting). That omission is not a protocol fail when UI evidence is not required. When it is required, the issue stays `status:pending-acceptance`.
- **Logs**: file under `logs/` covering the judged window so `TEL.1`–`TEL.5` can be correlated.
- **Notes**: `notes.md` — what was judged, blockers, and non-blocking marks only when the protocol allows.

## Retention

Keep the run folder in-repo until the accept outcome for that issue is recorded. Do not delete it before then.

## Cite from acceptance

`accept-project-issue` cites the run folder (and `manifest.md`) when QA was required. It records acceptance only after any protocol-required UI screenshots for the same build are present. A product or interface fail still blocks acceptance and may file a defect without those screenshots. Procedures: [`procedures.md`](procedures.md).
