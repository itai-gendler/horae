---
appliesTo:
- type: entity
  id: time-entry
  effect: changes
  from: Invoiced
  to: Open
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#transition_invoice
---

# Only managers and admins release invoiced time

Invoiced time returns to open only when a manager or admin voids its invoice.
