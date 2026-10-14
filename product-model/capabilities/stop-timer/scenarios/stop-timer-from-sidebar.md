---
kind: alternative
routes:
  web: Web
steps:
- text: The Member chooses Stop timer in the sidebar
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team
- text: The Product records the elapsed whole minutes as the duration
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: changes, facts: [Duration, Start time, Running, Timer start]}
  contexts:
    web:
      place: web::team
references:
- kind: code
  role: implementation
  target: crates/horae/src/components/timer_widget.rs
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries.rs#stop_entry_timer
---

# Stop a timer from the sidebar

## Trigger

A person chooses Stop timer in the sidebar.

## Outcome

The sidebar returns to Start timer and the entry holds the elapsed time.
