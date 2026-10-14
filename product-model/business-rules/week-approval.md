---
appliesTo:
- type: entity
  id: weekly-timesheet
  effect: changes
  to: Approved
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#ensure_can_approve
- kind: code
  role: implementation
  target: crates/core/src/state.rs#can_transition
---

# Only managers and admins approve a submitted week

Approving a week is reserved to managers and admins.
