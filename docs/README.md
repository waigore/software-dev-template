# `docs/`

Project and process documentation (labels, issues, skills, repo setup). Product/technical specifications live in [`specs/`](../specs/).

## Concise docs

Every file under `docs/` must stay under **500 words**. If content would exceed that, split into multiple focused files and link between them. CI enforces this for Markdown (`word-limit` in [Spec lint](spec-lint.md)); run `python3 .github/scripts/spec_lint.py` locally.

## Index

| Path | Covers |
|------|--------|
| [mcp.md](mcp.md) | Project MCP wiring for Cursor / OpenCode / Grok; auth rules; declared servers; smoke test |
| [coding-conventions.md](coding-conventions.md) | Project-owned coding conventions and lint/format/unit-test/coverage tooling; extends `solid.md` |
| [demo.md](demo.md) | Product demo mode: config-bounded slice of the main product; `specs/product/demo.md` |
| [pocs.md](pocs.md) | Proofs of concept under `pocs/`: requests, scope, relaxed bars, optional promotion |
| [poc-promotion.md](poc-promotion.md) | Optional PoC reconcile act; keep/drop/adapt; reimplementation |
| [dev-env-setup.md](dev-env-setup.md) | Local stack install/verify; then `setup-unit-test-ci` |
| [open-design-skill-setup.md](open-design-skill-setup.md) | User-local Open Design skill + content under `~/.open-design-skill/`; optional agent wiring |
| [ux-mockups.md](ux-mockups.md) | Mockup catalog approval; main-tree UI gate; verification and PoC promotion |
| [github-repo-setup.md](github-repo-setup.md) | First-time GitHub settings to apply and verify (remotes, Actions, `main` ruleset, squash, auto-merge, labels) |
| [github-repo-setup-examples.md](github-repo-setup-examples.md) | Non-binding example commands for the setup |
| [issues/](issues/) | Epic / Task / Defect contract and status workflow |
| [labels.md](labels.md) | Label catalog and sync |
| [pull-requests.md](pull-requests.md) | PR flow, branch names, body contract, auto-merge holds |
| [requirements/](requirements/README.md) | Unconfirmed requirement notes awaiting capture into specs (not specs) |
| [qa/evidence/](qa/evidence/) | QA protocol evidence (story IDs, pass/fail, notes, logs, optional UI screenshots); requirements in `specs/qa/` |
| [quality/evidence/](quality/evidence/) | Quality-evaluator evidence: per-axis pass, fail, or blocked for deterministic verification and llm-judge acceptance |
| [skills.md](skills.md) | Skill authoring and native wiring |
| [../agent-orc/](../agent-orc/) | agent-orc daemon: spin up workflow skill agents ([usage](../agent-orc/docs/usage.md)) |
| [solid.md](solid.md) | SOLID principles + structure continuity for agents; owned by the template |
| [spec-lint.md](spec-lint.md) | CI checks for spec structure (rules line, templates, links, glossaries) |
