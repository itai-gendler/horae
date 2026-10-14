---
domain: invoices
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#transition_invoice
---

# Void invoice

A manager or admin cancels a draft or sent invoice, returning its time to open.
