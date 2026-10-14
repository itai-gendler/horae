---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Retry import on a failed import
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: [Record errors]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product queues the import again
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Failed, to: Queued, facts: []}
  contexts:
    web:
      place: web::administration::importers
---

# Retry a failed import

## Trigger

An admin chooses Retry import on a failed import.

## Outcome

The import is queued again.
