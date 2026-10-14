---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Deactivate on an active client
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::clients
- text: The Product deactivates the client
  kind: product
  actor: manager
  entities:
  - {entity: client, effect: changes, from: Active, to: Inactive, facts: []}
  contexts:
    web:
      place: web::team::clients
---

# Deactivate a client

## Trigger

A manager chooses Deactivate on an active client.

## Outcome

The client is inactive; its projects take no new time and it is offered for no new project or invoice.
