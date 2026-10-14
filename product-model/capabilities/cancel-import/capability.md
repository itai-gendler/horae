---
domain: importers
availability:
- {place: 'web::administration'}
- {place: admin-cli}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#cancel_harvest_import_job
---

# Cancel import

An admin asks a queued or running import to stop.
