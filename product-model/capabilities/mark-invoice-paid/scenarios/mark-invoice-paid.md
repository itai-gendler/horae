---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Mark Paid on a sent invoice
  kind: actor
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: [Number, Total]}
  contexts:
    web:
      place: web::team::invoice
- text: The Product marks the invoice paid
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: changes, from: Sent, to: Paid, facts: []}
  contexts:
    web:
      place: web::team::invoice
---

# Mark a sent invoice paid

## Trigger

A manager chooses Mark Paid on a sent invoice.

## Outcome

The invoice is paid and offers no further status changes.
