---
domain: importers
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#harvest_change_account
- kind: code
  role: implementation
  target: crates/horae/src/importers/harvest/account_switch.rs
---

# Change Harvest account

An admin switches the connection to a different Harvest account.
