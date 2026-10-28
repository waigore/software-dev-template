# Authoring rules: product traceability

Read this before editing `specs/product/traceability.md`. Do not copy these rules into the spec.

Also read [product.md](product.md).

This file shows how product aligns with `specs/vision.md` and `specs/definition/definition.md`, and which specs cover each required topic.

## Alignment

Every essential quality, in-scope item, and user objective is served by at least one spec. Nothing serves only a vision non-goal or a definition out-of-scope item.

Each row names the upstream item, its source (`vision` or `definition`), and links to the product specs that serve it.

## Topic coverage

Each topic in the table is covered, or marked N/A. Fill Applicability with "Applies" or "N/A — reason". The reason is grounded in the domain and product profile or in the definition. Do not delete a topic row to skip it. Mark it N/A.

Outcomes in product match the definition's user objectives. Where qualities conflict, follow the vision's tradeoff order. Every product spec states what it serves.

## Splitting

If the file passes 500 words, move the alignment table to `traceability/alignment.md`. Leave a one-line summary and a link, and update `product.md`.
