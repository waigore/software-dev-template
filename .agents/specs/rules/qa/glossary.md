# Authoring rules: QA glossary

Read this before editing `specs/qa/glossary.md` or a domain file split from it. Do not copy these rules into the spec.

Also read [qa.md](qa.md).

Shared language for QA specs. Each term is defined once here. Other specs use it exactly and link here.

Product terms stay in `specs/product/glossary.md`. UX terms stay in `specs/ux/glossary.md`. Do not redefine them here; cite those glossaries when a protocol needs a product or interface term.

The skeleton already defines Coverage mode, Evidence run, Graphical run, Headless run, Manifest, Product protocol, Situational tool, Story row, Telemetry event, and UX protocol. Keep those rows. Add a row for a term this project needs. Keep added rows alphabetical. One term per concept: no synonyms.

Columns: term, a one-sentence definition, and where it is detailed (a link, or "here").

## Splitting

If the file passes 500 words, split added terms into `glossary/<domain>.md`. Keep `glossary.md` as the index, and update links.
