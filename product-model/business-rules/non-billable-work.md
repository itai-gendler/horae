---
appliesTo:
- type: capability
  id: track-time
- type: capability
  id: edit-time-entry
- type: entity
  id: time-entry
  facts:
  - Billable
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#choices
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries.rs#update_entry
---

# Time on a non-billable project or task is never billable

An entry is billable only when the person marks it billable and its project task is billable on a project that is not non-billable.
