---
entities:
- entity: time-entry
  shows:
  - Date
  - Project task
  - Duration
  - Start time
  - Notes
  - Billable
  - Running
  - Position
  collects:
  - Date
  - Project task
  - Duration
  - Start time
  - Notes
- entity: project
  shows:
  - Name
- entity: task
  shows:
  - Name
- entity: client
  shows:
  - Name
entryPoints:
- web: /timesheet/week
- web: /timesheet/day
- web: /timesheet/calendar
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/timesheet.rs#Timesheet
- kind: code
  role: implementation
  target: crates/horae/src/pages/timesheet/data.rs
---

# Timesheet

A person's own time for a day, a week or a calendar span, with each day's and the week's
totals, the project and task choices they may track on, and whether the week has been
submitted.
