---
domain: importers
availability:
- {place: 'web::administration'}
- {place: admin-cli}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#start_harvest_api_import
- kind: code
  role: implementation
  target: crates/horae/src/importers/harvest.rs
- kind: code
  role: implementation
  target: crates/horae/src/importers/harvest/apply.rs
- kind: code
  role: implementation
  target: crates/horae/src/cli/imports.rs
- kind: spec
  role: intent
  target: specs/004-harvest-importer/spec.md
---

# Import from Harvest

An admin pulls clients, projects, tasks and time entries from the connected Harvest account, first as a preview and then for real, from Importers or the command line.
