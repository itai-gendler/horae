---
kind: edge
routes:
  web: Web
steps:
- text: The Member chooses Submit week for approval
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Member's weekly timesheet for that week is approved
  kind: condition
  actor: member
  entities:
  - {entity: weekly-timesheet, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product refuses the submission
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
---

# Resubmitting an approved week is refused

## Trigger

A person submits a week that is already approved.

## Outcome

Nothing changes; the week must be reopened before it can be submitted again.
