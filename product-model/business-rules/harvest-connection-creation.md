---
appliesTo:
- type: entity
  id: harvest-connection
  effect: creates
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#harvest_connect_start
---

# Only admins connect Harvest

Connecting the organization to Harvest is reserved to admins.
