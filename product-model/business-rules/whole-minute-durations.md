---
appliesTo:
- type: capability
  id: track-time
- type: capability
  id: reschedule-time-entry
- type: capability
  id: stop-timer
- type: entity
  id: time-entry
  facts:
  - Duration
  - Start time
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries.rs#normalize_start
- kind: code
  role: implementation
  target: crates/core/src/time_of_day.rs#snap
- kind: code
  role: implementation
  target: crates/core/src/duration.rs#minutes_between
---

# Durations are whole minutes within one day

Durations are kept as whole minutes; a timed entry starts on the 15-minute grid and is shortened so it ends by midnight; a stopped timer counts elapsed whole minutes.
