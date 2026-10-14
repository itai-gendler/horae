---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters the person's email, name and role and chooses Create User
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::user-management
- text: The Product creates an active account with that email, name and role
  kind: product
  actor: admin
  entities:
  - {entity: account, effect: creates, to: Active, facts: [Name, Email, Role]}
  contexts:
    web:
      place: web::administration::user-management
---

# Invite a user

## Trigger

An admin chooses Invite User on User Management and enters an email, a name and a role.

## Outcome

The person has an active account with that role and can sign in with that email.

## Edge cases

- No invitation message is sent; the person signs in through single sign-on with the same email.
