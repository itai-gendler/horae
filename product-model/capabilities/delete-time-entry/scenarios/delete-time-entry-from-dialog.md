---
kind: primary
routes:
  web: Web
steps:
- text: The Member deletes an open time entry
  kind: actor
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product removes the time entry
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: removes, from: Open}
  contexts:
    web:
      place: web::team::timesheet
---

# Delete a time entry from its dialog

## Trigger

A person opens one of their open time entries and deletes it.

## Outcome

The entry is gone from the timesheet and the totals.
