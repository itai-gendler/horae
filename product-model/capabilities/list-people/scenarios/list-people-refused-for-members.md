---
kind: validation
routes:
  api: Harvest API
steps:
- text: The Member requests a page of users
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

# Listing people through the API is closed to members

## Trigger

An integration signed in as a member requests users.

## Outcome

The request is refused as forbidden.
