---
kind: edge
routes:
  web: Web
steps:
- text: The Manager generates an invoice for a client and period
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: [Name]}
  - {entity: invoice, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::invoices
- text: Some of the selected time entries changed after they were gathered
  kind: condition
  actor: manager
  entities:
  - {entity: time-entry, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::invoices
- text: The Product creates nothing and asks the Manager to retry
  kind: product
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::invoices
---

# Generating against time that changed meanwhile

## Trigger

Time in the period changes while a manager generates an invoice.

## Outcome

No invoice is created and the manager is asked to retry.
