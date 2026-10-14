---
domain: invoices
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#generate_invoice
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#generate_invoice_with_request
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices/entries.rs
---

# Generate invoice

A manager or admin generates a draft invoice for a client from the billable time and fees of a period.
