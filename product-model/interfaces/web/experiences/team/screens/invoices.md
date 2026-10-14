---
entities:
- entity: invoice
  shows:
  - Number
  - Issue date
  - Due date
  - Total
  collects:
  - Period
- entity: client
  shows:
  - Name
- entity: project
  shows:
  - Name
  - Fee balance
entryPoints:
- web: /invoices
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/invoices.rs#InvoiceList
- kind: code
  role: implementation
  target: crates/horae/src/pages/invoices/preparation.rs
---

# Invoices

The organization's invoices, and where a new invoice is prepared for a client and period.
