---
kind: validation
routes:
  api: Harvest API
steps:
- text: The Member requests time entries for another person
  kind: actor
  actor: member
  entities: []
  contexts:
    api:
      place: harvest-api
- text: The Product refuses the request as forbidden
  kind: product
  actor: member
  entities: []
  contexts:
    api:
      place: harvest-api
---

# A member asking for a colleague's time is refused

## Trigger

An integration signed in as a member requests another person's time entries.

## Outcome

The request is refused as forbidden rather than answered with other rows.
