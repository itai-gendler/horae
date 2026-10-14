---
appliesTo:
- type: entity
  id: harvest-connection
  effect: changes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#harvest_change_account
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#harvest_disconnect
---

# Only admins change or disconnect the Harvest connection

Switching or removing the Harvest connection is reserved to admins.
