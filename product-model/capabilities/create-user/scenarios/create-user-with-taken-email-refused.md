---
kind: validation
routes:
  web: Web
steps:
- text: The Admin creates a user with an email already in use
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::user-management
- text: Another account has that email
  kind: condition
  actor: admin
  entities:
  - {entity: account, effect: reads, facts: [Email]}
  contexts:
    web:
      place: web::administration::user-management
- text: The Product refuses to create it
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::user-management
---

# Creating a user with a taken email is refused

## Trigger

An admin creates a user with an email another account already has.

## Outcome

No account is created and the admin is told the email is taken.
