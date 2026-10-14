---
appliesTo:
- type: entity
  id: time-entry
  effect: removes
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
  target: crates/horae/src/server_fns/time_entries/commands.rs#apply
---

# Only the person who tracked it deletes a time entry

A person deletes their own open time entries; nobody deletes another person's time.
