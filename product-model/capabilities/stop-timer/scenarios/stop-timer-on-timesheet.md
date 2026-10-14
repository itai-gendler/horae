---
kind: primary
routes:
  web: Web
steps:
- text: The Member stops the running time entry
  kind: actor
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Running]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product records the elapsed whole minutes as the duration and the timer's start, on the 15-minute grid, as the start time
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: changes, facts: [Duration, Start time, Running, Timer start]}
  contexts:
    web:
      place: web::team::timesheet
---

# Stop a timer on the timesheet

## Trigger

A person stops their running timer on the timesheet.

## Outcome

The entry is no longer running; its duration is the elapsed whole minutes and it sits on the calendar at the time the timer started.

## Edge cases

- A timer that ran past midnight keeps no start time and stays untimed.
- A person can stop their own timer even after losing access to its project task.
