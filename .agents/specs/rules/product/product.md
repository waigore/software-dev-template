# Authoring rules: product

Read this before editing `specs/product/product.md`. Do not copy these rules into the spec.

Every other file under `specs/product/` follows **Rules for every product spec** below. Those rules files name this one under **Also read**.

Product describes how the software works for users: features, flows, entities, and scenarios. It is downstream of `specs/vision.md`, `specs/definition/definition.md`, and `specs/definition/quality.md`. If product conflicts with them, change product, or revise the upstream document first.

## Rules for every product spec

- **Self-contained**: describe every rule, entity, and behavior in full, even when the domain is well known. Do not rely on an external reference (a competitor, a wiki, a link). A comparison may help, but the spec must stand without it. At `prototype`, a formalized spec may adopt a named convention and state only the deltas. At `small` and `full`, the spec stands without that reference.
- **Product, not UX**: describe what happens and why. User actions are verbs (submit, invite, approve), not inputs, buttons, screens, menus, or layouts. Interface structure lives under `specs/ux/`.
- **Conceptual and logical**: no frameworks, code, data formats, or platform APIs. Platforms appear only as product implications in the profile below. A limit imposed by an architecture decision is stated in product terms and cites its ID, such as `(ADR-0003)`.
- **Shared language**: define each term once in `glossary.md` and each entity in `entities/`. Other specs link. They never redefine.
- **Traceable**: every spec states which vision qualities and definition scope items it serves. `traceability.md` maps all of them.
- **Identified and proven**: every behavior-defining element has a stable ID per [ids.md](ids.md) and is proven by Given/When/Then product stories per [stories.md](stories.md) and [story-coverage.md](story-coverage.md).
- **Concise**: each file stays under 500 words. Split by logical unit and link. The type's own rules file says where to move the extra part.

## Domain and product profile

Fill this in `product.md`:

- **Domain / product type**.
- **Conventions adopted**: the convention, then how this product applies it.
- **Conventions rejected or changed**: the convention, then why, traced to the vision.
- **Platform implications**: for each platform in the definition, the conceptual effect on product. Shape: "Mobile → sessions are short; drafts autosave." No hardware and no input mapping.

Adopted and rejected conventions show up in the specs that implement them. Platform implications show up in flows, features, and configuration.

## Index

Keep the global-spec list. For a unit spec, copy that folder's `_template.md` to `<kebab-name>.md`, fill the copy, and add the link under the matching heading. Leave `_template.md` unchanged.

If the index pushes `product.md` past 500 words, move the index to `specs/product/index.md` and leave a link in `product.md`.
