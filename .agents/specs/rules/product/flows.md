# Authoring rules: flow

Read this before editing `specs/product/flows/_template.md` or `specs/product/flows/<name>.md`. Do not copy these rules into the spec.

Also read [product.md](product.md) and [ids.md](ids.md). Stories follow [story.md](story.md).

Copy the template to `flows/<kebab-name>.md`, one file per flow. Do not fill the template in place.

A flow is a sequence of product phases and the transitions between them: onboarding, a request lifecycle, a checkout, or stage-to-stage work. Phases are states of the product process, not screens.

## Header

- **Scope**: product, session, request, workflow, or other.
- **Parent flow**: a link, or "None".
- **Serves**: vision qualities and definition scope items.

## Sections

- **Overview**: one paragraph from start to finish.
- **Phases**: `P1`, `P2`, …. Columns: purpose, the verbs the user can do (name verbs that are explicitly unavailable), and a link to a child flow or related feature when useful. Every phase is reachable. Every phase has an exit unless it ends the flow. Each listed verb is available. A verb named as unavailable does not change product state.
- **Transitions**: `T1`, `T2`, …. Columns: from, to, trigger, conditions, which state fields carry over or reset, and the user-outcome intent. A phase that does not end the flow has a transition out.
- **Entry and exit**: `N1`, `N2`, …. How the flow starts and its starting state, and one entry per way it ends, with the outcome.
- **Interruptions**: `U1`, `U2`, …. What happens to product state if work is suspended, abandoned, or interrupted.
- **Diagram**: optional. A mermaid `stateDiagram` of phases and transitions. The tables are authoritative. Delete the section when there is no diagram.
