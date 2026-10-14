---
appliesTo:
- type: entity
  id: weekly-timesheet
  effect: removes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#reject_submission
---

# Only managers and admins reopen a submitted or approved week

Reopening a week removes its weekly timesheet and is reserved to managers and admins.
