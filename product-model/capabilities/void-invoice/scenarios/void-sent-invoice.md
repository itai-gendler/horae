---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager chooses Void on a sent invoice
  kind: actor
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: [Number]}
  contexts:
    web:
      place: web::team::invoice
- text: The Product voids the invoice
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: changes, from: Sent, to: Void, facts: []}
  contexts:
    web:
      place: web::team::invoice
- text: The Product returns the voided bill's time entries to open and clears their rounded durations
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, effect: changes, from: Invoiced, to: Open, facts: [Rounded duration]}
  contexts:
    web:
      place: web::team::invoice
---

# Void a sent invoice

## Trigger

A manager chooses Void on a sent invoice.

## Outcome

The invoice is void and its time is open again.
