---
appliesTo:
- type: entity
  id: weekly-timesheet
  effect: reads
  contexts:
  - {place: 'web::team::approvals'}
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#list_approvals
- kind: code
  role: implementation
  target: crates/horae/src/pages/approvals.rs
---

# Only managers and admins see submitted weeks

Approvals lists every submitted week in the organization to managers and admins, and nothing to members.
