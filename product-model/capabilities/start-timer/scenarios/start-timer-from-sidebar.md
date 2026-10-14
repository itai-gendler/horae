---
kind: alternative
routes:
  web: Web
steps:
- text: The Member chooses Start timer in the sidebar and picks a project and task with optional notes
  kind: actor
  actor: member
  entities:
  - {entity: project, effect: reads, facts: [Name]}
  - {entity: task, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::team
- text: The Product records a running open time entry for today
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: creates, to: Open, facts: [Date, Project task, Duration, Notes, Billable, Running, Timer start, Position]}
  contexts:
    web:
      place: web::team
references:
- kind: code
  role: implementation
  target: crates/horae/src/components/timer_widget.rs
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries.rs#insert_time_entry
---

# Start a timer from the sidebar

## Trigger

A person chooses Start timer in the sidebar from any page of the workspace.

## Outcome

The sidebar shows the running timer with its project and task.
