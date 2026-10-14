---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Connect Harvest
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::importers
- text: The Product sends the Admin to Harvest to authorize read-only access and receives the authorization back
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::importers
- text: The Product stores the Harvest connection
  kind: product
  actor: admin
  entities:
  - {entity: harvest-connection, effect: creates, to: Connected, facts: [Harvest account]}
  contexts:
    web:
      place: web::administration::importers
---

# Connect Harvest

## Trigger

An admin chooses Connect Harvest on Importers.

## Outcome

Horae holds read-only access to the Harvest account and reads nothing until an import runs.

## Edge cases

- Reconnecting after a disconnect must authorize the same Harvest account the organization was bound to.
