---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager saves a fee line exceeding the project's remaining fee balance
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Fee balance]}
  contexts:
    web:
      place: web::team::invoice
- text: The Manager confirms the over-invoicing
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::invoice
- text: The Product saves the values with the confirmed excess
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: changes, facts: [Lines, Total]}
  contexts:
    web:
      place: web::team::invoice
---

# Confirm billing a fee beyond its balance

## Trigger

A manager saves a fee line larger than what remains of the project's fees.

## Outcome

The draft is saved once the manager confirms the exact excess.
