---
appliesTo:
- type: entity
  id: invoice
  effect: changes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#update_invoice_status
---

# Only managers and admins change an invoice's status

Marking an invoice sent or paid and voiding it are reserved to managers and admins.
