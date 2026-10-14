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
  target: crates/horae/src/pages/timesheet.rs
---

# Reschedule time entry

A person drags a timed entry on the calendar to another time or day, or drags its edge to change its duration.
