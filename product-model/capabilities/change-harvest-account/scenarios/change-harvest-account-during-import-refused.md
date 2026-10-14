---
kind: edge
routes:
  web: Web
steps:
- text: The Admin chooses to connect a different Harvest login
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::importers
- text: An import from the Harvest connection is queued or running
  kind: condition
  actor: admin
  entities:
  - {entity: import, effect: reads, facts: []}
  - {entity: harvest-connection, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::importers
- text: The Product refuses the change
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::importers
---

# Changing the Harvest account during an active run is refused

## Trigger

An admin changes the Harvest account while a Harvest import is queued or running.

## Outcome

The connection stays as it was; the admin is asked to finish or cancel the run first.
