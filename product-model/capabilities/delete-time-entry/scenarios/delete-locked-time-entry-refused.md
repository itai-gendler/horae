---
kind: edge
routes:
  web: Web
steps:
- text: The Member tries to delete a locked time entry
  kind: actor
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
- text: The time entry is not open, or its week is submitted or approved
  kind: condition
  actor: member
  entities:
  - {entity: time-entry, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product refuses the deletion
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
---

# Deleting a locked time entry is refused

## Trigger

A person tries to delete a time entry that is submitted, approved or invoiced.

## Outcome

The entry stays.
