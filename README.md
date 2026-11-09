# ai-repo-template

A GitHub Template Repository that gives every new project the same small, AI-friendly documentation standard. It ships structure and guidance, never project-specific content.

> This README describes the template. In a repository created from it, replace or delete this file.

## Why this exists

AI coding agents and new teammates need the same thing: one place to learn how the project is documented, what is true, and what to leave out. Without a standard, each agent decides for itself and you get empty docs or clutter. This template fixes the conventions once and reuses them.

It follows existing conventions instead of inventing new ones:

- [AGENTS.md](https://agents.md/) is the single instruction file for AI agents.
- [Diátaxis](https://diataxis.fr/) separates guides, reference and explanation.
- [C4 model](https://c4model.com/) structures architecture documentation.
- [MADR](https://adr.github.io/madr/) 4.0.0 records architecture decisions.
- GitHub Issues and Projects track tasks. There are no roadmap or to-do Markdown files.

## What you get

```text
AGENTS.md                  Rules for AI agents (10 fixed sections)
docs/README.md             Documentation index and where things go
docs/HOW-TO-DOCUMENT.md    When and what to document, and when docs should grow
docs/architecture/         C4 overview
docs/decisions/            MADR template and decision register
docs/guides/               How-to format rules (guides appear when real)
docs/reference/            Reference format rules (pages appear when real)
docs/local/                Local-only notes, never committed
.github/                   Issue forms and pull request template
extensions/                Optional add-ons by project type
```

## Supported project types

Core files suit any project. Extensions add templates for a project type:

| Extension | Use when the project is |
|---|---|
| `extensions/spring-boot` | A backend service (API, database, migrations) |
| `extensions/frontend` | A user interface, with a locked register of approved decisions |
| `extensions/feature-specs` | Built feature by feature from written specs |
| `extensions/ml-experiments` | ML, deep learning or data science work |
| `extensions/research` | Literature review and research writing |

Install only what the project needs. Each extension README lists its detection signals, install command and the lines to register.

## Use as a GitHub Template

1. On GitHub, open this repository and choose **Use this template**, then **Create a new repository**.
2. Clone your new repository.
3. Add the local exclusion (this file is not versioned, so it is not inherited):

   ```sh
   printf 'docs/local/*\n!docs/local/README.md\n' >> .git/info/exclude
   ```

4. Adopt it for the project (below).

"Use this template" copies the committed files only. It does not copy issues, labels, Projects, branch protection, secrets or `.git/info/exclude`. The issue forms use the labels `bug` and `enhancement`; create them if they do not exist.

This template has no `CLAUDE.md`. Claude Code reads `CLAUDE.md`, not `AGENTS.md`. If you use it, add a one-line `CLAUDE.md` that imports `AGENTS.md`.

## Adopt in a new project

Give this prompt to your AI agent in the new repository:

```text
Adopt the documentation template for this project.
1. Inspect the repository and classify the project type. Report what you found.
2. Install only the extensions that match, following each extension README.
3. Fill AGENTS.md section 1 from real files. Do not invent; write "Unknown, verify" where unsure.
4. Draft docs/architecture/overview.md from verified code and configuration only.
5. Read docs/HOW-TO-DOCUMENT.md. Create only the docs that pass its worth-documenting test today.
6. List the remaining gaps for me instead of inventing content.
7. Delete this template README and the unused extensions/ folders.
```

## Customize without breaking the core

- Keep the ten `AGENTS.md` section headings and their order. Add project detail inside them.
- Keep one owner per fact. Link instead of copying.
- Add documentation when a growth trigger in `docs/HOW-TO-DOCUMENT.md` fires, not in advance.
- Core files never link into `extensions/`, so deleting that folder is safe.
- Keep YAML front matter out of docs, except inside MADR records.

## Template repository versus created repository

| | This template | A repository created from it |
|---|---|---|
| Root `README.md` | Explains the template | Describes your project |
| `extensions/` | All add-ons present | Delete it after installing what you need |
| `AGENTS.md` section 1 | Fill-in fields | Real project facts |
| `docs/architecture/overview.md` | Prompts | Real architecture |
| `docs/decisions/` | Template only | Your ADRs |
| `docs/guides/`, `docs/reference/` | Format rules only | Real guides and reference |

## License

See [LICENSE](LICENSE).
