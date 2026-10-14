---
appliesTo:
- type: capability
  id: edit-invoice
- type: capability
  id: generate-invoice
- type: entity
  id: project
  facts:
  - Fee balance
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices/editing.rs
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices/fees.rs
---

# Billing a fee beyond its remaining balance needs an explicit confirmation

A fee line that exceeds what remains of a project's fees is saved or generated only after the exact excess is confirmed.
