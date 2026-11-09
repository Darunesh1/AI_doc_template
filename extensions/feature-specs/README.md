# Extension: Feature specifications

A lightweight, Spec Kit-inspired structure for features that need written requirements before coding. Each feature gets a spec (what and why) and a plan (how). Task status is not tracked here; use GitHub Issues.

## When to use

Install when features are non-trivial enough that requirements, acceptance criteria and constraints should be agreed before implementation. Skip it for small changes that an issue and a PR describe well enough.

## Install

From the repository root:

```sh
cp -rn extensions/feature-specs/specs .
```

This adds `specs/_template/spec.md` and `specs/_template/plan.md`.

## Use

For each feature:

```sh
cp -r specs/_template specs/NNN-feature-name
```

Use the next unused three-digit number and a short name with dashes, for example `specs/001-user-export`. Fill in `spec.md` first and agree it. Then fill in `plan.md`. Open a GitHub Issue for the work and link it from the spec.

## Register

1. In `AGENTS.md` section 1, change "Active extensions" to include `feature-specs`.
2. Add to `AGENTS.md` section 4: "For a feature that has a spec in `specs/`, read its `spec.md` and `plan.md` before coding, and implement against the acceptance criteria."
3. In `docs/README.md`, change "Active extensions" to include `feature-specs`.

## Fill from the project

- Requirements and constraints come from the person requesting the feature and the existing system. Ask, and do not invent.
- Affected components and interfaces come from reading the code.
- Mark unknowns as `Unknown, verify` and list them under open questions.

## Growth triggers

- A spec that records a significant choice between options: write an ADR in `docs/decisions/` and link it from the spec.
- A finished feature: update the permanent docs it changed, and keep the spec as the record of intent.

## Uninstall

Delete the `specs/` folder and remove the register lines.
