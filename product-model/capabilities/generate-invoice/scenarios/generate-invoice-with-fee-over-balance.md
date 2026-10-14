---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager prepares an invoice whose fee lines exceed a project's remaining fee balance
  kind: actor
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Fee balance]}
  - {entity: invoice, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::invoices
- text: The Manager chooses Confirm excess and generate
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::invoices
- text: The Product creates the draft with the confirmed excess
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: creates, to: Draft, facts: [Number, Period, Issue date, Due date, Lines, Payment terms, Purchase order, Discount and taxes, Total]}
  contexts:
    web:
      place: web::team::invoices
---

# Generate an invoice billing a fee beyond its balance

## Trigger

A manager prepares an invoice whose fee lines exceed what remains of a project's fees.

## Outcome

The draft is generated once the manager confirms the exact excess.
