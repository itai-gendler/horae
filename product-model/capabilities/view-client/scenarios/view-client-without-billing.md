---
kind: alternative
routes:
  web: Web
steps:
- text: The Member opens a client
  kind: actor
  actor: member
  entities:
  - {entity: client, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::client
- text: The Product shows the client's profile and its projects only
  kind: product
  actor: member
  entities:
  - {entity: client, effect: reads, facts: [Name, Currency, Billing address]}
  - {entity: project, effect: reads, facts: [Name, Code]}
  contexts:
    web:
      place: web::team::client
---

# View a client without its billing

## Trigger

A member opens a client.

## Outcome

The member sees the client's profile and projects, without its default rate or invoices.
