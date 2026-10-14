---
appliesTo:
- type: entity
  id: import
  effect: changes
permits:
- actors:
  - admin
- unattended: true
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#cancel_harvest_import_job
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#retry_harvest_import_job
---

# Only admins cancel or retry imports

Cancelling and retrying imports is reserved to admins.
