---
appliesTo:
- type: capability
  id: start-timer
- type: entity
  id: time-entry
  facts:
  - Running
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries.rs#start_timer
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#create
---

# A person runs at most one timer

Starting a timer while another of one's own is running is refused; the running one is not stopped.
