# API conventions

Conventions the generated API specification cannot express. Link to the generated contract; do not copy it. Answer each item from the real code and delete items that do not apply.

Contract source: link to the generated spec, or write `Unknown, verify`.

## Base path and versioning

- What is the base path?
- How is the API versioned (path, header, none)?
- What counts as a breaking change here?

## Authentication and authorization

- How does a caller authenticate?
- Where is authorization enforced, and by what rule?

## Request and response format

- Content types accepted and returned.
- Naming conventions for fields and resources.
- Date, time and identifier formats.

## Errors

- The error response shape, with one real example.
- Which status code is used for which kind of failure.

## Pagination, filtering and sorting

- How lists are paginated, filtered and sorted.
- Default and maximum page size.

## Idempotency and concurrency

- Which operations are safe to retry.
- How concurrent updates are detected, if at all.

## Deprecation

- How an endpoint is marked deprecated and how long it is kept.
