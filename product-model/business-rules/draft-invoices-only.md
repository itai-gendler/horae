---
appliesTo:
- type: capability
  id: edit-invoice
- type: entity
  id: invoice
  facts:
  - Payment terms
  - Purchase order
  - Discount and taxes
  - Lines
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices/editing.rs
---

# Only a draft invoice's values change

Once an invoice is sent, paid or void, its values are fixed.
