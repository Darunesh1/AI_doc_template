# AGENTS.md

Canonical instructions for AI coding agents in this repository.
Consult [docs/README.md](docs/README.md) before deciding where new documentation belongs.

## 1. Project Context

Fill every field from the real repository (code, config, build files). Do not invent. Write `Unknown, verify` when a fact cannot be confirmed.

- Purpose: what the project does and for whom.
- Project type: for example service, library, web app, ML pipeline, research.
- Stack: languages, frameworks, datastores actually in use.
- Run and test commands: the exact commands that work today.
- Active extensions: none.

## 2. Documentation Structure

- `docs/README.md`: documentation index; start here.
- `docs/HOW-TO-DOCUMENT.md`: when and what to document.
- `docs/architecture/`: how the system is shaped (C4 overview).
- `docs/decisions/`: architecture decision records (MADR) and the decision register.
- `docs/guides/`: how-to procedures. Created only when real instructions exist.
- `docs/reference/`: lookup material. Created only when real content exists.
- `docs/local/`: local-only notes, never committed.
- Extensions are named here only after they are adopted.

## 3. Source of Truth

- Order of authority: running code, then schemas and migrations, then ADRs, then prose docs.
- Each fact has exactly one owning document. Link to it; do not copy it.
- Generated documentation (API specs, schema dumps) is linked, not duplicated.
- Tasks, roadmaps and known issues live in GitHub Issues and Projects, not in Markdown files.
- Planned functionality is not implemented functionality. Never describe it as done.

## 4. Development Rules

- Read the relevant documentation before modifying code.
- Verify an existing implementation by reading the code before making claims about it.
- Make the smallest change that satisfies the request.
- Respect existing database schemas and migrations. Add a new migration; never edit an applied one.
- Follow the conventions already present in the code before introducing new ones.
- Do not add dependencies or tools unless they solve a clearly identified problem.

## 5. Architecture and Decision Rules

- System-level structure is documented in `docs/architecture/overview.md` using C4 levels 1 and 2.
- Add component-level documentation only when complexity justifies it.
- Record every significant architectural decision as an ADR in `docs/decisions/` following MADR.
- Check existing ADRs before proposing a change that may conflict with one.
- Never edit an accepted ADR to change its meaning. Supersede it with a new ADR.

## 6. Data and Security Rules

- Never commit secrets, credentials, tokens, defence-related sensitive information or restricted datasets.
- Never replace real project data with fabricated data when performing validation.
- Use synthetic data only when it is explicitly appropriate and say so.
- Do not paste real personal or sensitive data into issues, PRs, docs or logs.
- Report suspected leaked secrets immediately instead of working around them.

## 7. Testing and Verification

- Run the tests relevant to your change and read the results.
- Never mark a feature complete without verifying the implementation and its relevant tests.
- State what you ran and what you saw. Do not claim success without evidence.
- If a test cannot be run, say so and say why.

## 8. Documentation Maintenance

- Before creating or changing any doc, read [docs/HOW-TO-DOCUMENT.md](docs/HOW-TO-DOCUMENT.md).
- Update documentation in the same PR as the code change it describes.
- Do not duplicate information across documents.
- Do not create empty or placeholder documents.

## 9. Repository Boundaries

- Do not modify sibling repositories unless explicitly authorized.
- Files outside this repository are not part of its implementation.
- Do not treat a path outside the repository root as a dependency you may edit.

## 10. Local Documentation Rules

- `docs/local/` holds local-only material and is never committed.
- Do not cite `docs/local/` as a source of truth for the project.
- Anything the team needs permanently belongs in the proper `docs/` folder instead.
