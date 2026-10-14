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
  target: crates/horae/src/server_fns/time_entries/commands.rs#create
- kind: code
  role: implementation
  target: crates/horae/src/pages/timesheet.rs#persist_entry
---

# Track time

A person adds a time entry for a day on a project task they may track on, by typing a duration.
