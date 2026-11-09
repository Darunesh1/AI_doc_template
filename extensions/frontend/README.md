# Extension: Frontend

Documentation for user interface flows and a locked register of approved UI decisions, so approved designs and labels are not changed by accident.

## When to use

Install when the project has a user interface. Detection signals: a UI framework dependency in `package.json`, a components folder, route definitions, or design files.

## Install

From the repository root:

```sh
cp -rn extensions/frontend/docs/. docs/
```

This adds `docs/guides/ui-flows.md` and `docs/reference/ui-decisions.md`.

## Register

1. In `AGENTS.md` section 1, change "Active extensions" to include `frontend`.
2. Add the rules below to `AGENTS.md` section 4.
3. In `docs/README.md`, change "Active extensions" to include `frontend`.

Frontend rules for `AGENTS.md`:

- Read `docs/reference/ui-decisions.md` before changing any screen, label, copy or layout.
- Never change a locked entry. Changing one needs the owner's approval and a superseding ADR.
- Reuse existing components before creating new ones.
- Do not invent copy, labels or flows; take them from the approved design or ask.

## Fill from the project

| Template field | Where to look |
|---|---|
| Flows and screens | Route definitions, navigation components, design files |
| Existing components | Components folder, any component catalogue the project keeps |
| Labels and copy | Translation files, component source |
| Design system | Link the design tool file or token source, if any |

## Growth triggers

Create these when the need appears, not before:

- `docs/reference/component-conventions.md`, when a second contributor needs to know naming, props, state and file layout rules. Answer from the existing components.
- `docs/reference/design-system.md`, when design tokens or a shared library exist. Contain links to the source of truth only (tokens, design file, catalogue); do not copy values.
- `docs/guides/ui-testing.md`, when UI test steps exist and take more than a few lines to explain.

## Uninstall

Delete `docs/guides/ui-flows.md` and `docs/reference/ui-decisions.md`, then remove the register lines.
