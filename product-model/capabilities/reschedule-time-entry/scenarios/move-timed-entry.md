---
kind: primary
routes:
  web: Web
steps:
- text: The Member drags a timed entry to another slot
  kind: actor
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: [Date, Start time]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product saves the new date and start time, snapped to the 15-minute grid
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: changes, facts: [Date, Start time, Duration]}
  contexts:
    web:
      place: web::team::timesheet
---

# Move a timed entry on the calendar

## Trigger

A person drags one of their open timed entries to another time or day on the calendar.

## Outcome

The entry sits at the new date and start time.

## Edge cases

- The duration is shortened when the new start would carry the entry past midnight.
