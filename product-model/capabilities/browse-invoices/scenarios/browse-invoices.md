---
kind: primary
routes:
  web: Web
steps:
- text: The Manager opens Invoices
  kind: actor
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::invoices
- text: The Product lists the invoices with their client, dates and totals
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: [Number, Issue date, Due date, Total]}
  - {entity: client, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team::invoices
---

# Browse invoices

## Trigger

A manager opens Invoices.

## Outcome

The manager sees each invoice's number, client, dates, status and total.
