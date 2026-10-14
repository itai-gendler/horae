---
domain: invoices
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#save_invoice_draft
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#review_invoice_edit
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices/editing.rs
- kind: code
  role: implementation
  target: crates/horae/src/pages/invoices/editing.rs
---

# Edit invoice

A manager or admin changes a draft invoice's values before it is sent.
