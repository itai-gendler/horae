---
domain: importers
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/importers.rs#harvest_connect_start
- kind: code
  role: implementation
  target: crates/horae/src/importers/harvest/oauth.rs
- kind: doc
  role: intent
  target: specs/004-harvest-importer/quickstart.md
---

# Connect Harvest

An admin authorizes Horae to read the organization's Harvest account. It exists only while the deployment configures Harvest import credentials.
