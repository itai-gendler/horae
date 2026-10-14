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
  target: crates/horae/src/server_fns/time_entries.rs#start_timer
- kind: code
  role: implementation
  target: crates/horae/src/components/timer_widget.rs
---

# Start timer

A person starts a timer on a project task for today; the running entry counts up until stopped.
