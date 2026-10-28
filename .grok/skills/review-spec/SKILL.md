---
name: review-spec
description: |-
  Review a spec document (or the formalized spec set) under specs/ against its
  review instructions in .agents/specs/, then report the verdict back to the
  requester (chat, GitHub issue, PR, or calling agent). Whole-spec review also
  runs the applicability, terminology, and TBD audits on formalized sections;
  any Fail fails the overall verdict. Placeholder-only files are not formalized
  and are not a Fail.
  Use when the user asks to review, check, or validate a spec such as the vision,
  definition, product, UX, QA, ADR, or technical design docs.
---

# Review spec (facade)

Canonical instructions: [`.agents/skills/review-spec/SKILL.md`](../../../.agents/skills/review-spec/SKILL.md).

Read that file and its `references/` as needed, then run the workflow there. Do not invent a parallel process.
