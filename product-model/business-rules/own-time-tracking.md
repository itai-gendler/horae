---
appliesTo:
- type: entity
  id: time-entry
  effect: creates
  contexts:
  - {place: 'web::team'}
permits:
- related:
  - {verb: owns, entity: member}
- related:
  - {verb: owns, entity: manager}
- related:
  - {verb: owns, entity: admin}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#begin
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries.rs#insert_time_entry
---

# People track time only for themselves

Every new time entry belongs to the person who adds it or starts its timer; nobody adds time for someone else.
