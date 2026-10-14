---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Cancel on a running import
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: [Counts]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product stops the import as cancelled
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Running, to: Cancelled, facts: []}
  contexts:
    web:
      place: web::administration::importers
---

# Cancel an import

## Trigger

An admin chooses Cancel on a running import.

## Outcome

The import stops at a safe point and shows as cancelled.
