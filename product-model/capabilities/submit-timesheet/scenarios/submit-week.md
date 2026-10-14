---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses Submit week for approval on the week view
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::timesheet
- text: The Product submits every open time entry of the week, freezing each rounded duration by the organization's rounding rule
  kind: product
  actor: member
  entities:
  - {entity: time-entry, effect: changes, from: Open, to: Submitted, facts: [Rounded duration]}
  - {entity: organization, effect: reads, facts: [First day of the week, Rounding increment, Rounding direction]}
  contexts:
    web:
      place: web::team::timesheet
- text: The Product records the Member's weekly timesheet as awaiting approval
  kind: product
  actor: member
  entities:
  - {entity: weekly-timesheet, effect: creates, to: Awaiting approval, facts: [Week, Submitted at, Total time, Billable time]}
  contexts:
    web:
      place: web::team::timesheet
---

# Submit a week for approval

## Trigger

A person whose week holds open time chooses Submit week for approval.

## Outcome

The week's open entries are submitted with their rounded durations frozen, and the week awaits approval.

## Edge cases

- Entries already invoiced in the week stay invoiced; only open entries are submitted.
- A week with no open entries cannot be submitted.
