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
  target: crates/horae/src/server_fns/time_entries.rs#reorder_entries
---

# Reorder untimed entries

A person rearranges a day's untimed entries on the calendar, or drags one to another day.
