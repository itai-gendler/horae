---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Disconnect
  kind: actor
  actor: admin
  entities:
  - {entity: harvest-connection, effect: reads, facts: [Harvest account]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product removes the stored authorization and keeps which Harvest login it was bound to
  kind: product
  actor: admin
  entities:
  - {entity: harvest-connection, effect: changes, from: Connected, to: Disconnected, facts: []}
  contexts:
    web:
      place: web::administration::importers
---

# Disconnect Harvest

## Trigger

An admin chooses Disconnect on Importers.

## Outcome

Horae no longer holds access to Harvest; CSV imports remain available.
