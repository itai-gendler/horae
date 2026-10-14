---
appliesTo:
- type: entity
  id: import
  effect: reads
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#list_harvest_import_jobs
---

# Only admins see imports and their reports

The import history and reports are shown only to admins.
