---
domain: approvals
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#approve_submission
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#approve_submissions
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/approvals.rs#approve_periods
---

# Approve timesheet

A manager or admin approves submitted weeks, one at a time or every pending week shown.
