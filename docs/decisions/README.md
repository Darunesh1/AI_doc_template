# Architecture decisions

Architecture Decision Records follow [MADR](https://adr.github.io/madr/) 4.0.0. Do not invent another format. The rule for when a decision deserves a record is in [../HOW-TO-DOCUMENT.md](../HOW-TO-DOCUMENT.md).

## Writing a record

1. Copy [0000-template.md](0000-template.md) to `NNNN-short-title-with-dashes.md`.
2. Use the next unused four-digit number, starting at `0001`.
3. Fill in the sections. Remove optional sections you do not need.
4. Set `status` in the record's own front matter, using the MADR values: proposed, rejected, accepted, deprecated, or superseded by ADR-NNNN.
5. Add one row to the register below.

## Changing a decision

- Never edit an accepted record to change its meaning.
- Write a new record and set the old record's status to `superseded by ADR-NNNN`.
- Status lives only in each record. The register does not repeat it.

## Register

| No | Title | Link |
|---|---|---|
| 0000 | Template (not a decision) | [0000-template.md](0000-template.md) |
