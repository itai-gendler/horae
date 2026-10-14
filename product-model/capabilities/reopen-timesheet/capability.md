---
domain: approvals
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#reject_submission
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#reopen_period
---

# Reopen timesheet

A manager or admin sends a submitted or approved week back to its person, unlocking its time.
