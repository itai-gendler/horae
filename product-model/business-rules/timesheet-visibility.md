---
appliesTo:
- type: entity
  id: time-entry
  effect: reads
  contexts:
  - {place: 'web::team::timesheet'}
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
  target: crates/horae/src/server_fns/permissions/time_entries.rs#sheet
---

# A timesheet shows only its own person's time

On the timesheet everyone, managers and admins included, sees only their own entries.
