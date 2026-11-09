# Guides

Format rules for how-to documents. The purpose of this folder and where other content goes are in [../README.md](../README.md).

Create a guide only when real, verified instructions exist. Do not create stubs.

## Naming

Use short lowercase names with dashes that state the goal, for example `setup.md`, `deploy.md`, `troubleshooting.md`.

## Skeleton

1. Goal: one sentence on what the reader achieves.
2. Prerequisites: what must already be true or installed.
3. Steps: numbered, one action each, with the exact commands.
4. Verify: how the reader confirms it worked, with the expected output.
5. Troubleshooting: known failure modes and fixes.

## Rules

- Commands must be ones that work today. Run them before documenting them.
- Explain why only in a sentence; deeper reasoning belongs in `architecture/` or `decisions/`.
- Link to reference material instead of copying it.
