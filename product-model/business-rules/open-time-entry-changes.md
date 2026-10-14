---
appliesTo:
- type: entity
  id: time-entry
  effect: changes
  facts:
  - Date
  - Project task
  - Duration
  - Start time
  - Notes
  - Billable
  - Running
  - Timer start
  - Position
permits:
- related:
  - {verb: owns, entity: member}
  when: &id001
  - {state: Open}
- related:
  - {verb: owns, entity: manager}
  when: *id001
- related:
  - {verb: owns, entity: admin}
  when: *id001
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#apply
---

# Only the person who tracked it changes an open time entry

A time entry's own facts change only while it is open, and only by the person it belongs to.
