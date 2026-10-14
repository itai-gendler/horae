---
kind: validation
routes:
  web: Web
steps:
- text: The Member opens Approvals
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::approvals
- text: The Product shows that reviewing access is required and lists nothing
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::approvals
---

# Approvals are closed to members

## Trigger

A member opens Approvals.

## Outcome

No weeks are listed; the page says manager or admin access is required.
