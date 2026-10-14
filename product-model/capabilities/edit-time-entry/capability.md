---
domain: timesheet
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#apply
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#save
---

# Edit time entry

A person changes one of their own open time entries.
