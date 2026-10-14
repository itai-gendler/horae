---
domain: invoices
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#update_invoice_status
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#transition_invoice
---

# Mark invoice paid

A manager or admin records that a sent invoice was paid.
