---
kind: validation
routes:
  web: Web
steps:
- text: The Manager opens a timesheet link naming a colleague
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The timesheet names a person other than the Manager
  kind: condition
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product refuses the timesheet and shows no entries
  kind: product
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::timesheet
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/permissions/time_entries.rs#sheet
---

# Opening another person's timesheet is refused

## Trigger

A signed-in person opens a timesheet link that names another person.

## Outcome

No entries of the other person are shown; the timesheet asks for a refresh.
