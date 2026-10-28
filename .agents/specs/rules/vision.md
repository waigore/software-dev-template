# Authoring rules: vision

Read this before editing `specs/vision.md`. Do not copy these rules into the spec.

The vision is the north star. Every other spec and feature must trace back to it.

Keep the file under 500 words. Replace every `<!-- fill in -->`. Delete unused rows.

## Elevator pitch

One or two sentences. State the core user value and why it is compelling. A reader must understand it without the rest of the document. Shape: "A \<product type\> that helps \<audience\> \<core outcome\>."

## High-level description

One paragraph, at most 150 words. Cover the core use, the context, the tone, and what makes the product distinct. Describe the experience. Do not write a feature list. Stay consistent with the elevator pitch.

## Target audience and user promise

- **Audience**: who uses this. Name role, experience level, and usage habits. "Everyone" is not an audience.
- **User promise**: what the user gets to achieve or feel. An outcome or role, not a feature list.

## Essential qualities

At most **5**. Each quality is testable: a reviewer can judge whether a feature supports or undermines it.

Keep three rows. Add rows 4 and 5 only when needed. Delete unused rows.

Each row has a name, a one-line description, and a "supports it if…" test. The test is observable: two reviewers would reach the same judgment on a given feature. Qualities are distinct, and they follow from the pitch and the description.

## Tradeoffs

When qualities conflict, the higher-priority one wins. List pairs in priority order: quality over quality, then why. Every likely conflict has a stated winner. The order must not cycle.

## Non-goals

What this product is not. Features that only serve a non-goal are rejected. State at least one non-goal. Non-goals must not contradict the pitch, the description, or the qualities.
