---
kind: primary
routes:
  web: Web
steps:
- text: The Manager enters the new client's name, currency, optional default rate and billing address and chooses Create client
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::clients
- text: The Product creates the active client record
  kind: product
  actor: manager
  entities:
  - {entity: client, effect: creates, to: Active, facts: [Name, Currency, Default rate, Billing address]}
  contexts:
    web:
      place: web::team::clients
---

# Create a client

## Trigger

A manager chooses New client on Clients and enters its name, currency, default rate and billing address.

## Outcome

The client is active and can be chosen for projects and invoices.
