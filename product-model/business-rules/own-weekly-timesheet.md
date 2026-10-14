---
appliesTo:
- type: entity
  id: weekly-timesheet
  effect: creates
permits:
- related:
  - {verb: submits, entity: member}
- related:
  - {verb: submits, entity: manager}
- related:
  - {verb: submits, entity: admin}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#submit_week
---

# People submit only their own week

A weekly timesheet is created only by the person whose week it is.
