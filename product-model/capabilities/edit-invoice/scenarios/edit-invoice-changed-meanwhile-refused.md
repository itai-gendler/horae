---
kind: edge
routes:
  web: Web
steps:
- text: The Manager chooses Save invoice values
  kind: actor
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::invoice
- text: The invoice, its status or the fee balances changed since the Manager reviewed it
  kind: condition
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::invoice
- text: The Product refuses the save
  kind: product
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::invoice
---

# Saving an invoice that changed meanwhile

## Trigger

A manager saves invoice values after the invoice or its fee balances changed.

## Outcome

Nothing is saved; the manager is asked to reload or review again.
