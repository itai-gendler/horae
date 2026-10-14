---
domain: invoices
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#list_invoices
- kind: code
  role: implementation
  target: crates/horae/src/pages/invoices.rs#InvoiceList
---

# Browse invoices

A manager or admin looks through the organization's invoices.
