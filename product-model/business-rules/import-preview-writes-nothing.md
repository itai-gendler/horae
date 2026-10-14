---
appliesTo:
- type: capability
  id: import-from-harvest
- type: capability
  id: import-harvest-csv
- type: entity
  id: import
  facts:
  - Mode
references:
- kind: spec
  role: intent
  target: specs/004-harvest-importer/spec.md
- kind: code
  role: implementation
  target: crates/horae/src/importers/harvest/streaming/durable/preview.rs
---

# A preview import writes nothing

Previewing an import reports what a commit would do without creating or changing any record.
