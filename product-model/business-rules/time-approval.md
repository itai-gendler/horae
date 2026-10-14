---
appliesTo:
- type: entity
  id: time-entry
  effect: changes
  to: Approved
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#approve_periods
---

# Only managers and admins approve submitted time

Submitted time becomes approved only through a manager's or admin's approval of its week.
