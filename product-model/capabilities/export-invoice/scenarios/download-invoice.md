---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses Download PDF or a spreadsheet export
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::invoice
- text: The Product produces the invoice file
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: [Number, Issue date, Due date, Lines, Payment terms, Purchase order, Discount and taxes, Total]}
  - {entity: client, effect: reads, facts: [Name, Billing address]}
  contexts:
    web:
      place: web::team::invoice
---

# Download an invoice

## Trigger

A manager chooses Download PDF, or a CSV or XLSX export, on an invoice.

## Outcome

A file with the invoice's number, client, dates, lines and totals downloads.
