---
kind: validation
routes:
  web: Web
steps:
- text: The Admin starts a Harvest API import
  kind: actor
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::importers
- text: Harvest is not connected
  kind: condition
  actor: admin
  entities:
  - {entity: harvest-connection, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::importers
- text: The Product refuses to queue the import
  kind: product
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::importers
---

# Importing from Harvest without a connection is refused

## Trigger

An admin starts a Harvest API import while Harvest is not connected.

## Outcome

No import is queued; the admin is asked to connect Harvest first.
