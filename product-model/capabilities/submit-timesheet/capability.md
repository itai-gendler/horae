---
domain: timesheet
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#submit_week
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#submit_user_week
- kind: code
  role: implementation
  target: crates/horae/src/pages/timesheet.rs
---

# Submit timesheet

A person submits their week for approval, locking its open time.
