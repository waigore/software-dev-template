# Authoring rules: QA traceability

Read this before editing `specs/qa/traceability.md`. Do not copy these rules into the spec.

Also read [qa.md](qa.md).

How QA aligns with the vision, definition, quality, product, and UX.

## Alignment

Every QA global and protocol serves a vision quality, a definition scope item, a product spec, or a UX spec. Nothing serves only a non-goal or an out-of-scope item.

Each row names the upstream item, its source (`vision`, `definition`, `product`, or `ux`), and links to the QA specs that serve it. Map tools, procedures, evidence, coverage, and every protocol file.

## Topic coverage

Each topic in the table is covered, or marked N/A. Fill Applicability with "Applies" or "N/A — reason". The reason is grounded in the definition, product, or UX. Do not delete a topic row to skip it.

## Splitting

If the file passes 500 words, move the alignment table to `traceability/alignment.md`. Leave a summary and a link, and update `qa.md`.
