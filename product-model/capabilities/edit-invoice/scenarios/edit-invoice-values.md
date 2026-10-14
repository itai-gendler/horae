---
kind: primary
routes:
  web: Web
steps:
- text: The Manager changes payment terms, purchase order, discount, taxes or fee lines and chooses Review invoice
  kind: actor
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: [Payment terms, Purchase order, Discount and taxes, Lines, Total]}
  contexts:
    web:
      place: web::team::invoice
- text: The Manager chooses Save invoice values
  kind: actor
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::invoice
- text: The Product saves the values and recalculates the totals
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: changes, facts: [Payment terms, Purchase order, Discount and taxes, Lines, Total]}
  contexts:
    web:
      place: web::team::invoice
---

# Edit a draft invoice's values

## Trigger

A manager chooses Edit invoice values on a draft invoice.

## Outcome

The draft carries the new payment terms, purchase order, discount, taxes and fee lines, with recalculated totals.
