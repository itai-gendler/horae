---
appliesTo:
- type: capability
  id: import-from-harvest
- type: capability
  id: import-harvest-csv
- type: entity
  id: import
  facts:
  - Counts
references:
- kind: code
  role: implementation
  target: crates/horae/src/importers/harvest/provenance.rs
- kind: spec
  role: intent
  target: specs/004-harvest-importer/spec.md
---

# Imported records are matched by their Harvest identity and never duplicated

Running an import again recognizes records it brought in before, even when they were edited in Horae, and creates only what is new.
