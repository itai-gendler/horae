---
appliesTo:
- type: entity
  id: project
  effect: reads
  facts:
  - Billing rates
  - Notes
  - Fee balance
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects.rs#get_project_fee_balances
- kind: code
  role: implementation
  target: crates/horae/migrations/0035_project_read_access.sql
---

# Only managers and admins see project rates, notes and fee balances

A project's billing rates, private notes and fee balances are shown only to managers and admins.
