# Documentation index

Entry point for humans and AI agents. Read this before deciding where new documentation belongs. For judgement on whether to write something at all, read [HOW-TO-DOCUMENT.md](HOW-TO-DOCUMENT.md).

## Directories

| Directory | Purpose |
|---|---|
| [architecture/](architecture/overview.md) | How the system is shaped: purpose, boundaries, containers, technology, constraints. |
| [decisions/](decisions/README.md) | Why it is shaped that way: architecture decision records and the register. |
| [guides/](guides/README.md) | Practical procedures: setup, running, deployment, troubleshooting, workflows. |
| [reference/](reference/README.md) | Material you look up: glossary, configuration, API contracts, schemas, terminology. |
| [local/](local/README.md) | Local-only notes. Never committed. |

## Where does a new document go?

| The reader wants to... | Diátaxis type | Put it in |
|---|---|---|
| Achieve a goal by following steps | How-to guide | `guides/` |
| Look up a fact, term, contract or setting | Reference | `reference/` |
| Understand why the system is shaped this way | Explanation | `architecture/` |
| Understand why a choice was made over alternatives | Explanation | `decisions/` |
| Learn by doing a guided exercise | Tutorial | Not used by default. Add `docs/tutorials/` only if the project needs one. |
| Keep a private or temporary note | Not documentation | `local/` |

If none fits, the content probably does not belong in the repository. See the worth-documenting test in [HOW-TO-DOCUMENT.md](HOW-TO-DOCUMENT.md).

## Conventions

- Diátaxis: documentation types are kept apart. A guide does not explain theory; a reference does not give instructions.
- C4: architecture documentation uses C4 levels 1 (System Context) and 2 (Container). Add component or code level only when complexity justifies it.
- MADR: significant decisions are recorded as Markdown Architectural Decision Records. See [decisions/README.md](decisions/README.md).
- Plain Markdown by default. YAML front matter appears only inside MADR records.
- Tasks, roadmaps and known issues live in GitHub Issues and Projects, not here.

## Extensions

Active extensions: none.

Extensions add optional templates for a project type. Add one only when the project needs it:

1. Copy the extension's payload into the repository root, as described in its README.
2. Add the register lines its README lists to `AGENTS.md` and to this section.
3. Remove what you do not use.

Core documents do not link into `extensions/`, so deleting that folder breaks nothing.
