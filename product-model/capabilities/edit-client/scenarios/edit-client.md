---
kind: primary
routes:
  web: Web
steps:
- text: The Manager changes the client's details and chooses Save changes
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: &id001 [Name, Currency, Default rate, Billing address]}
  contexts:
    web:
      place: web::team::clients
- text: The Product saves the client's new details
  kind: product
  actor: manager
  entities:
  - {entity: client, effect: changes, facts: *id001}
  contexts:
    web:
      place: web::team::clients
---

# Edit a client

## Trigger

A manager chooses Edit on a client and changes its details.

## Outcome

The client shows its new details.
