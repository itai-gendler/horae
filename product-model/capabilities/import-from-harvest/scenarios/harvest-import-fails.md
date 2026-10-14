---
kind: edge
routes:
  web: Web
steps:
- text: The Admin follows a running import on Importers
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: [Counts]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product stops the import as failed
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: changes, from: Running, to: Failed, facts: [Record errors]}
  contexts:
    web:
      place: web::administration::importers
---

# An import from Harvest fails

## Trigger

A running import cannot continue, for example because Harvest withdrew the authorization.

## Outcome

The import stops as failed and keeps a report of what it reached.
