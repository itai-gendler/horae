---
appliesTo:
- type: entity
  id: time-entry
  effect: reads
  contexts:
  - {place: harvest-api}
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: owns, entity: member}
references:
- kind: code
  role: implementation
  target: crates/horae/src/harvest/mod.rs#scoped_user_filter
---

# Through the API, members read only their own time while managers and admins read everyone's

The Harvest-style API answers a member with their own time entries and a manager or admin with the whole organization's.
