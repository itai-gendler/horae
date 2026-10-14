---
appliesTo:
- type: entity
  id: time-entry
  effect: changes
  from: Submitted
  to: Open
- type: entity
  id: time-entry
  effect: changes
  from: Approved
  to: Open
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#reopen_period
---

# Only managers and admins return submitted or approved time to open

Submitted and approved time opens again only when a manager or admin reopens its week.
