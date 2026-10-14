---
availability:
- {place: harvest-api}
references:
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#list_time_entries
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#scoped_user_filter
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#time_entry_by_id
---

# List time entries

An integration acting with a person's session reads time entries through the Harvest-style API.
