---
kind: primary
routes:
  web: Web
steps:
- text: The Admin reviews the current Harvest connection and chooses to connect a different Harvest login
  kind: actor
  actor: admin
  entities:
  - {entity: harvest-connection, effect: reads, facts: [Harvest account]}
  contexts:
    web:
      place: web::administration::importers
- text: The Product binds the Harvest connection to the newly authorized Harvest login
  kind: product
  actor: admin
  entities:
  - {entity: harvest-connection, effect: changes, facts: [Harvest account]}
  contexts:
    web:
      place: web::administration::importers
---

# Change the Harvest account

## Trigger

An admin chooses Change account and connect after reviewing the current connection.

## Outcome

The connection reads the newly authorized Harvest account.
