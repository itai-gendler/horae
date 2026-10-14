---
kind: validation
routes:
  web: Web
steps:
- text: The Member completes sign-in at the identity provider
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::signed-out::sign-in
- text: The matching account is deactivated
  kind: condition
  actor: member
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-out::sign-in
- text: The Product returns the Member to the sign-in page without a session
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::signed-out::sign-in
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#resolve_identity
---

# Sign in refused for a deactivated account

## Trigger

A person whose account has been deactivated completes single sign-on.

## Outcome

The person stays signed out on the sign-in page.
