---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Mark Sent on a draft invoice
  kind: actor
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: [Number, Total]}
  contexts:
    web:
      place: web::team::invoice
- text: The Product marks the invoice sent
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: changes, from: Draft, to: Sent, facts: []}
  contexts:
    web:
      place: web::team::invoice
---

# Mark a draft invoice sent

## Trigger

A manager chooses Mark Sent on a draft invoice.

## Outcome

The invoice is sent.
