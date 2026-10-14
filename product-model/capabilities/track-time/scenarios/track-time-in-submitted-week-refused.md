---
kind: edge
routes:
  web: Web
steps:
- text: The Member enters time for a day in a week they submitted
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The day lies in one of the Member's submitted or approved weeks
  kind: condition
  actor: member
  entities:
  - {entity: weekly-timesheet, effect: reads, facts: [Week]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product refuses the entry and adds nothing
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/time_entries/commands.rs#apply
---

# Adding time to a submitted week is refused

## Trigger

A person tries to add time on a day whose week they have already submitted.

## Outcome

No time entry is added; the timesheet reports that the week's approval blocks the change.
