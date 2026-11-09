# How to document

This playbook teaches judgement: when to write, what is worth writing, what to leave out, and when the docs should grow. Folder layout and purposes are in [README.md](README.md). Hard rules for agents are in [../AGENTS.md](../AGENTS.md).

## 1. The worth-documenting test

Write something down only if it is one of these:

- Not obvious from reading the code.
- A decision where real alternatives existed.
- A contract between parts: an API, a schema, another repository.
- How to run, test or deploy.
- A domain term someone new would not know.
- A constraint or invariant the code relies on.
- Something the user agreed and locked.

If none applies, do not write it. Silence is better than clutter.

## 2. What never to document

- Restatements of code, for example "UserService handles users".
- Generated documentation. Link to it instead.
- Task status, plans of the week or roadmaps. Those belong in GitHub Issues and Projects.
- Temporary work. Use `docs/local/` for that.
- Secrets, credentials or real sensitive data.
- Guesses. Write `Unknown, verify` and say how to find out.
- Chat transcripts and an agent's own reasoning steps.

## 3. Where it goes

Use the question-to-folder table in [README.md](README.md). Do not keep a second table here.

## 4. Growth triggers: when X happens, create Y

Start with the core files only. Add documents when a trigger fires.

| When | Create |
|---|---|
| The first real choice between options is made | The first ADR in `decisions/`, copied from `0000-template.md` |
| Setup steps are explained a second time | `guides/setup.md` |
| A folder develops its own rules | A nested `AGENTS.md` in that folder |
| A doc passes about 300 lines or covers two topics | Split it into two docs and link them |
| `AGENTS.md` nears 120 lines | Move detail into `docs/` and link to it |
| An external API, schema or contract appears | A page in `reference/`, or a link to the generated spec |
| Project signals match an extension | Install that extension (see below) |

Project signals. Each extension README is the owner of its own signals; this is only a lookup:

- `pom.xml` or `build.gradle`: `extensions/spring-boot`.
- A UI framework in `package.json`: `extensions/frontend`.
- Notebooks or training scripts: `extensions/ml-experiments`.
- `.bib` files or paper drafts: `extensions/research`.
- Features that need written requirements before coding: `extensions/feature-specs`.

## 5. Pruning

- A doc that contradicts the code is fixed in the same PR, or deleted.
- A replaced decision is superseded by a new ADR, never edited.
- A file nobody uses or links to is removed.
- When two docs answer the same question, keep one and link from the other.

## 6. Good and bad examples

All examples below are invented to show the quality bar.

Decision:

- Bad: "We use Postgres."
- Good: "Postgres over Mongo because KPI queries join 6 tables; see 0003."

Architecture:

- Bad: "The OrderService class manages orders."
- Good: "Orders are written by the API container and read by the reporting container through a read replica. Reporting must never write."

Guide:

- Bad: "Run the app and it should work."
- Good: "Run `make dev`. Expected: the API answers on port 8080 and `GET /health` returns 200. If port 8080 is busy, see Troubleshooting."

Reference:

- Bad: a pasted copy of the generated OpenAPI file.
- Good: "API contract: see the generated spec at `<link>`. Pagination and error conventions that the spec cannot express are listed below."

## 7. Before you finish

- Does every new doc pass section 1?
- Is any fact now stated in two places?
- Did you mark unverified facts as `Unknown, verify`?
- Did you update docs that your code change made wrong?
