---
appliesTo:
- type: entity
  id: invoice
  effect: reads
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#list_invoices
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs#get_invoice
---

# Only managers and admins see invoices

The invoice list and each invoice are shown only to managers and admins.
