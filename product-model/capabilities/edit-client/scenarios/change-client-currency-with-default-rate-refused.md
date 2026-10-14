---
kind: edge
routes:
  web: Web
steps:
- text: The Manager changes the currency of a client record that has a default rate
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::clients
- text: The client has a default rate
  kind: condition
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: [Default rate]}
  contexts:
    web:
      place: web::team::clients
- text: The Product refuses the currency change
  kind: product
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::clients
---

# Changing a client's currency while it has a default rate is refused

## Trigger

A manager changes the currency of a client that has a default rate.

## Outcome

The client keeps its currency and the manager is told why.
