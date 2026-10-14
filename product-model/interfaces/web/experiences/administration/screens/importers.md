---
entities:
- entity: harvest-connection
  shows:
  - Harvest account
- entity: import
  shows:
  - Source
  - Mode
  - Scope
  - Counts
  - Record errors
  collects:
  - Source
  - Mode
  - Scope
entryPoints:
- web: /admin/importers
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/importers.rs#HarvestImport
---

# Importers

The Harvest connection, the preview and commit of imports from the Harvest API or a Harvest CSV
export, and the import history with each import's report.
