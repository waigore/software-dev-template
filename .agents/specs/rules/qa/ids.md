# Authoring rules: QA element IDs

Read this before assigning or citing a QA element ID. Do not copy these rules into `specs/qa/ids.md` or into any other spec. That file only links here.

Also read [qa.md](qa.md).

Stable IDs let protocols, tools, and evidence name QA behavior exactly.

Product IDs stay in [../product/ids.md](../product/ids.md). UX IDs stay in [../ux/ids.md](../ux/ids.md). Cite them. Do not reuse their letters for a different meaning.

## Format

- **Spec key**: the prefix from the table below plus the file name without extension when under a folder. `product/core-flow.md` → `QAP-core-flow`. Global specs use the fixed key in the table.
- **Element ID**: a section letter or fixed name plus a number, unique within its spec. Use it bare inside the same spec. Elsewhere, qualify it, such as `QAP-core-flow.S2`.
- **Tool IDs**: fixed names from [`tools.md`](tools.md): `DBG.<n>`, `TEL.<n>`, `SIT.<n>`.
- **Protocol IDs**: the protocol file's key is the protocol ID. Steps use `S<n>`. Pass and fail criteria use `P<n>` and `F<n>` when listed as separate rows.

## Stability

- Never renumber or reuse an ID. A new element takes the next number after the highest ever used in that section.
- When an element is removed, delete it, leave the gap, and update every reference to it.
- When an element's meaning changes, keep its ID and update every protocol that uses it.

## Keys and identified sections

| Spec | Key | Sections and their ID letters |
|------|-----|-------------------------------|
| `tools.md` | `QA-tools` | Debug `DBG`, Telemetry `TEL`, Situational `SIT` (names as in the tools table) |
| `procedures.md` | `QA-proc` | Steps are ordered; no separate ID letters required beyond document order |
| `evidence.md` | `QA-ev` | Artifact kinds by name in the required-artifacts table |
| `coverage.md` | `QA-cov` | Critical entries `C` |
| `product/` | `QAP-<name>` | Steps `S`, Pass `P`, Fail `F`, Tools cited by `DBG`/`TEL`/`SIT` |
| `ux/` | `QAU-<name>` | Steps `S`, Pass `P`, Fail `F`, Tools cited by `DBG`/`TEL`/`SIT` |

Every section in this table gives each element an ID in this form when the section uses numbered rows. A qualified ID cited anywhere must exist. Cited product and UX story IDs must exist in those domains.
