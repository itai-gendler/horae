---
appliesTo:
- type: entity
  id: import
  effect: creates
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#start_harvest_api_import
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#start_harvest_csv_import
---

# Only admins start imports

Imports are queued only by admins, from Importers or the command line.
