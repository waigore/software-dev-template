# Product demo mode

A **demo** is a limited form of the **same** product: same architecture, specs, SOLID, tests, and code tree. What distinguishes it is application-level configuration that caps features or content (for example a trial window or one workspace). Authority: [`specs/product/demo.md`](../specs/product/demo.md). Config values live in [`specs/product/configuration.md`](../specs/product/configuration.md).

Not a proof of concept. PoCs live under `pocs/` and follow [`pocs.md`](pocs.md).

## When Offering is undecided or not offered

If `demo.md` Offering is `TBD` or **not offered**, do not implement demo mode. The rest of that spec may stay TBD or N/A.

## When offered

- Implement demo mode in the **main tree** like any other feature (ordinary issue workflow). No separate `create-demo` skill.
- Limitations in `DEMO.L*` are enforced only via the cited `CFG.*` parameters—no parallel ruleset ([Parity](../specs/product/demo.md)).
- Same bars as the full product: [`solid.md`](solid.md), [`coding-conventions.md`](coding-conventions.md), unit tests, `review-code`.
- Verification and acceptance follow the issue workflow against `demo.md` and the linked config.

## Entry and UX

Product states entry/exit in `DEMO.N1`. Screens and flows belong under `specs/ux/`.
