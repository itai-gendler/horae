---
kind: primary
routes:
  web: Web
steps:
- text: The Manager opens a client
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::client
- text: The Product shows the client's profile and default rate, its projects and its invoices
  kind: product
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: [Name, Currency, Billing address, Default rate]}
  - {entity: project, effect: reads, facts: [Name, Code]}
  - {entity: invoice, effect: reads, facts: [Number, Issue date, Total]}
  contexts:
    web:
      place: web::team::client
---

# View a client with its billing

## Trigger

A manager opens a client.

## Outcome

The manager sees the client's profile, default rate, projects and invoices.
