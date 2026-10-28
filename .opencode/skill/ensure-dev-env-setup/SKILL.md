---
name: ensure-dev-env-setup
description: |-
  Ensure local runtime stack tools from Accepted ADRs are installed and
  working, then run setup-unit-test-ci for Unit tests / Coverage CI. Use only
  when the user asks to set up or verify the dev environment; invent
  install/verify steps and transitive deps; best-effort install then report.
  Do not run as a gate for other skills.
---

# Ensure dev env setup (facade)

Canonical instructions: [`.agents/skills/ensure-dev-env-setup/SKILL.md`](../../../.agents/skills/ensure-dev-env-setup/SKILL.md).

Read that file and its `references/` as needed, then run the workflow there. Do not invent a parallel process.
