---
appliesTo:
- type: entity
  id: time-entry
  effect: creates
  contexts:
  - {place: 'web::administration'}
  - {place: admin-cli}
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/importers/harvest/apply.rs
---

# Only admins bring other people's time in through imports

Time created by an import belongs to the person the source record names, matched by email, and only an admin's import creates it.
