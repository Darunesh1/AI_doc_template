# Extension: Spring Boot / backend

Documentation conventions for backend services: API contract notes, database and migration practice, validation and testing. The templates ask questions; answer them from the real project and never assert a tool the project does not use.

## When to use

Install when the project is a backend service. Detection signals: `pom.xml` or `build.gradle` with Spring Boot, a `src/main/resources` configuration, REST controllers, or a migrations folder.

## Install

From the repository root:

```sh
cp -rn extensions/spring-boot/docs/. docs/
```

This adds `docs/reference/api-conventions.md` and `docs/guides/migrations.md`.

## Register

1. In `AGENTS.md` section 1, change "Active extensions" to include `spring-boot`.
2. Add the backend rules below to `AGENTS.md` section 4, trimmed to what is true for the project.
3. In `docs/README.md`, change "Active extensions" to include `spring-boot`.

Backend rules for `AGENTS.md`:

- Read `docs/reference/api-conventions.md` before changing an endpoint.
- Never change an applied migration. Add a new one.
- Keep controllers thin; do not put business rules in them.
- Validate input at the boundary and return errors in the documented error format.
- Do not change a public contract without updating the generated spec or reference doc in the same PR.

## Fill from the project

| Template field | Where to look |
|---|---|
| Base path, versioning | Controller mappings, gateway or ingress config |
| Authentication | Security configuration, filters |
| Error format | Exception handlers, existing error responses |
| Contract source | Generated spec, if the project produces one |
| Migration tool and location | Build dependencies, migrations folder, application config |
| Test commands | Build file, CI workflow |

## Validation and testing conventions

Document these in the project's own guide only once they are real. Answer from the code:

- Where does input validation live, and what does it reject?
- Which test levels exist (unit, slice, integration) and how is each run?
- How are external services and datastores handled in tests?
- Is real project data ever used in tests? Follow `AGENTS.md` section 6: never replace real data with fabricated data for validation; synthetic data only when explicitly appropriate.

## Growth triggers

Create these when the need appears, not before:

- `docs/reference/database-schema.md`, when the schema and migrations do not express something readers need: entity meaning, ownership, invariants, retention. Link to any generated schema documentation instead of copying it.
- `docs/guides/validation-and-testing.md`, when the test setup takes more than a few lines to explain.
- `docs/guides/deployment.md`, when real deployment steps exist.

## Uninstall

Delete `docs/reference/api-conventions.md` and `docs/guides/migrations.md`, then remove the register lines.
