# QA Glossary

Authoring rules: [`.agents/specs/rules/qa/glossary.md`](../../.agents/specs/rules/qa/glossary.md).

## Terms

| Term | Definition | Detailed in |
|------|------------|-------------|
| Coverage mode | Whether QA covers all in-scope product stories and UX journeys (`full`) or only marked critical IDs (`critical-only`). | [`coverage.md`](coverage.md), [`qa.md`](qa.md) |
| Evidence run | One issue/run folder under `docs/qa/evidence/` with manifest, notes, and logs, plus screenshots when a protocol requires UI evidence. | [`evidence.md`](evidence.md) |
| Graphical run | A QA session with a display that re-runs protocols and captures screenshots when UI evidence is required. | [`evidence.md`](evidence.md), [`procedures.md`](procedures.md) |
| Headless run | A QA session with no display. It may judge protocols and record pass/fail, notes, and logs. | [`evidence.md`](evidence.md), [`procedures.md`](procedures.md) |
| Manifest | The `manifest.md` index of story results and artifact paths for an evidence run. | [`evidence.md`](evidence.md) |
| Product protocol | An agent protocol that proves the build against a product story or element. | [`product/`](product/) |
| Situational tool | A capability required only when a protocol cites it (seed, replay, state dump). | [`tools.md`](tools.md) |
| Story row | One product or UX story/journey mapped to an epic/task owner or `none` with a durable reason. | [`story-rows.md`](story-rows.md) |
| Telemetry event | A QA-relevant runtime signal with the Must fields in `tools.md`. | [`tools.md`](tools.md) |
| UX protocol | An agent protocol that proves the build against a UX story or journey. | [`ux/`](ux/) |
