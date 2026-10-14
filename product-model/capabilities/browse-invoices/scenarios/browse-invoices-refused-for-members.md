---
kind: validation
routes:
  web: Web
steps:
- text: The Member opens the billing page
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::invoices
- text: The Product refuses the list
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::invoices
---

# Invoices are closed to members

## Trigger

A member opens Invoices.

## Outcome

No invoices are listed.
