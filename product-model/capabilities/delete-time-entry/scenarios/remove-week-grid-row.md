---
kind: alternative
routes:
  web: Web
steps:
- text: The Member removes a row from the week view
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product removes every time entry of the row in that week at once
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: removes, from: Open}
  contexts:
    web:
      place: web::team::timesheet
---

# Remove a week row

## Trigger

A person removes a project task row from the week view.

## Outcome

Every entry of that row in the week is deleted together, or none is.

## Edge cases

- A row holding any entry that cannot currently be removed is refused as a whole.
