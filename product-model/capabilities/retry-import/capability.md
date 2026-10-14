---
domain: importers
availability:
- {place: 'web::administration'}
- {place: admin-cli}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#retry_harvest_import_job
---

# Retry import

An admin runs a failed or cancelled import again.
