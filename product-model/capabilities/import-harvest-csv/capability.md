---
domain: importers
availability:
- {place: 'web::administration'}
- {place: admin-cli}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#start_harvest_csv_import
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers/csv_upload.rs
- kind: code
  role: implementation
  target: crates/horae/src/importers/harvest/csv_source.rs
---

# Import Harvest CSV

An admin uploads a Harvest CSV export and brings its records into Horae, first as a preview and then for real, from Importers or the command line.
