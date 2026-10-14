---
kind: alternative
routes:
  web: Web
steps:
- text: The Admin chooses Sign in as Admin on the sign-in page
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-out::sign-in
- text: The Product signs the Admin in to an active admin account
  kind: product
  actor: admin
  entities:
  - {entity: account, effect: reads, facts: [Role]}
  contexts:
    web:
      place: web::signed-out::sign-in
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth/dev.rs#dev_login_post
---

# Sign in as the development admin

## Trigger

A person opens Horae on a development installation where the one-click admin login is enabled.

## Outcome

The person is signed in as an active admin account and arrives at the timesheet.

## Edge cases

- With no active admin account the sign-in fails and asks for demo data to be seeded first.
