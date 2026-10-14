---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Activate on an inactive client
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::clients
- text: The Product reactivates the client
  kind: product
  actor: manager
  entities:
  - {entity: client, effect: changes, from: Inactive, to: Active, facts: []}
  contexts:
    web:
      place: web::team::clients
---

# Activate a client

## Trigger

A manager chooses Activate on an inactive client.

## Outcome

The client is active again.
