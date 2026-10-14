---
kind: primary
routes:
  web: Web
steps:
- text: The Member opens Clients and searches or filters the list
  kind: actor
  actor: member
  entities:
  - {entity: client, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::clients
- text: The Product lists the matching client records with their currency and status
  kind: product
  actor: member
  entities:
  - {entity: client, effect: reads, facts: [Name, Currency]}
  contexts:
    web:
      place: web::team::clients
---

# Browse clients

## Trigger

A signed-in person opens Clients and optionally searches by name or filters by status or currency.

## Outcome

The person sees the matching clients with their currency and whether they are active.
