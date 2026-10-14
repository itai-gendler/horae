---
appliesTo:
- type: entity
  id: time-entry
  effect: changes
  to: Invoiced
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#generate_invoice
- kind: code
  role: implementation
  target: crates/core/src/state.rs#can_transition
---

# Only managers and admins invoice time

Time becomes invoiced only through an invoice a manager or admin generates.
