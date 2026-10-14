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
  target: crates/horae/src/server_fns/time_entries.rs#stop_entry_timer
---

# Stop timer

A person stops their running timer and the elapsed time becomes the entry's duration.
