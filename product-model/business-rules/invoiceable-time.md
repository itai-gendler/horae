---
appliesTo:
- type: capability
  id: generate-invoice
- type: entity
  id: time-entry
  facts:
  - Billable
  - Running
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices/entries.rs
- kind: code
  role: implementation
  target: crates/core/src/state.rs#can_transition
---

# Only open and approved time is invoiced

Generating an invoice bills billable time that is open or approved and not running; submitted time waits for its approval decision and is left out.
