---
kind: primary
result: achieved
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
- text: The Product creates the draft invoice, invoices the billed time and opens the invoice
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: creates, to: Draft, facts: [Number, Period, Issue date, Due date, Lines, Payment terms, Purchase order, Discount and taxes, Total]}
  contexts:
    web:
      place: web::team::invoice
  capability: generate-invoice
- text: The Manager reviews the invoice's lines and total
  kind: actor
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: [Lines, Total]}
  contexts:
    web:
      place: web::team::invoice
- text: The Manager chooses Mark Sent and the Product marks the invoice sent
  kind: actor
  actor: manager
  entities:
  - {entity: invoice, effect: changes, from: Draft, to: Sent, facts: []}
  contexts:
    web:
      place: web::team::invoice
  capability: mark-invoice-sent
---

# Generate and send an invoice

## Trigger

A manager is ready to bill a client for a period's time.

## Outcome

The manager lands on the new draft invoice after generating it and marks it sent there.
