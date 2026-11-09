# Database migrations

How to change the database schema safely in this project. Fill in from the real setup. Delete steps that do not apply and write `Unknown, verify` where a fact is not confirmed.

## Goal

Change the schema through a new, versioned migration that applies cleanly on every environment.

## Prerequisites

- Which migration tool does the project use? Name it and link its configuration.
- Where do migration files live?
- How do you run a local database?

## Rules

- Never edit a migration that has been applied anywhere beyond your machine. Add a new migration.
- Keep each migration small and focused on one change.
- Make changes backward compatible with the running version where possible (add, then migrate data, then remove in a later release).
- Do not put real or sensitive data in migration files.

## Steps

1. Create a new migration file following the project's naming rule: `<state the pattern>`.
2. Write the change.
3. Apply it to a local database with: `<command>`.
4. Run the tests that touch the changed tables: `<command>`.

## Verify

State what the reader should see after a successful run, for example the migration listed as applied and the affected tests passing.

## Rollback

Describe how a failed or unwanted migration is handled in this project (down migration, forward fix, restore). Write `Unknown, verify` if no policy exists yet.

## Troubleshooting

List real failures seen in this project and their fixes. Leave this section out until there is one.
