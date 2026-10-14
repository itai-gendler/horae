---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses Sign out
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team
- text: The Product ends the Member's session
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team
---

# Sign out

## Trigger

A signed-in person chooses Sign out from their account menu.

## Outcome

The session ends and the person is back on the sign-in page.
