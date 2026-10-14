---
entities:
- entity: invoice
  shows:
  - Number
  - Period
  - Issue date
  - Due date
  - Lines
  - Payment terms
  - Purchase order
  - Discount and taxes
  - Total
  collects:
  - Lines
  - Payment terms
  - Purchase order
  - Discount and taxes
- entity: client
  shows:
  - Name
- entity: project
  shows:
  - Fee balance
entryPoints:
- web: /invoices/:id
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/invoices.rs#InvoiceDetail
---

# Invoice

One invoice with its lines and totals, and the status changes it still allows.
