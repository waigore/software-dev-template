# Applicability graph

Edges for [`audit-spec-applicability`](../SKILL.md). From [`.agents/specs/rules/`](../../../specs/rules/) — especially [quality.md](../../../specs/rules/quality.md), hub `traceability.md` rules, and [adr/decision.md](../../../specs/rules/adr/decision.md). Update when those rules change.

**Claim sites:** `specs/definition/quality.md` (and splits); product/UX/QA/ADR/technical `traceability.md` topic tables; ADR **Quality expectations**; optional technical hub lines.

## Quality categories

| Category | Upstream ground | Downstream when Applies | When N/A |
|----------|-----------------|-------------------------|----------|
| Performance | Vision / platforms / definition constraints | Stays in `quality.md`. Targets may cite product flows/modes. ADR Affects + Validation when an ADR limits the target | Reason cites vision or platforms; ADR row `N/A in quality.md` |
| Load time / latency | Same | Same as Performance | Same |
| Reliability | Same | Same as Performance | Same |
| Observability | Same; fidelity may scale | Stays in `quality.md`. Tools/sinks in ADRs. Optional `technical/verification.md` when warranted | Same |
| Save durability | Definition scope / progression that persists | Product progression or persistence stories (what/when/resume); UX save-failure Applies; technical `persistence` only if hub-indexed | Same reason on progression / UX save-failure; no filled durability target |
| Accessibility | Vision / audience / platforms | Product experience consequences; assists → product configuration; UX accessibility presentation | Same reason on experience and UX presentation |
| Localization | Vision / market / platforms | Product experience Localization; UX localization copy Applies | Same reason on experience and UX localization copy |

Performance, load time, reliability, and observability need no product/UX file beyond `quality.md`.

Every characteristic row cites exactly one axis in `specs/definition/quality/rubrics.md`. An N/A row's axis is not a downstream carry-out. When `specs/technical/verification.md` exists, each automatable deterministic axis is cited by an invariant there.

## Hub topic follow-ons

| Hub | Follow-on |
|-----|-----------|
| Product | Topic N/A cites product profile or definition. Sub-products "None" ⇒ topic N/A, no files |
| UX | Accessibility presentation, localization copy, save-failure follow quality |
| QA | Protocols and evidence follow product and UX stories that Apply |
| Technical | Optional globals Applies iff hub indexes the file. Diagrams Applies if any technical topic Applies. Persistence should agree with save durability when that Applies |
| ADR Stack | Area N/A grounded in definition or product profile |

## ADR Quality expectations

Per Accepted ADR in `specs/adr/decisions/`:

- Quality **Applies** → `Affects` or `No effect`. `Affects` cites the target; Validation covers it or cites that row's rubric axis.
- Quality **N/A** → `N/A in quality.md`.
- Mismatch either way → `ADR mismatch`.

## Audit order (whole set)

1. `quality.md` (definition/vision/platforms first).
2. Product → UX → QA topic tables.
3. Accepted ADR Quality rows.
4. Technical topics and optional globals vs hub index.
