---
kind: primary
routes:
  web: Web
steps:
- text: The Member chooses the single sign-on button on the sign-in page
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::signed-out::sign-in
- text: The Product sends the Member to the identity provider and receives the verified identity back
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::signed-out::sign-in
- text: The Product finds the active account already linked to that identity, or the unlinked active account with the same verified email, and links it
  kind: product
  actor: member
  entities:
  - {entity: account, effect: changes, facts: [Sign-in identity]}
  contexts:
    web:
      place: web::signed-out::sign-in
- text: The Product starts the Member's session and opens the timesheet
  kind: product
  actor: member
  entities:
  - {entity: account, effect: reads, facts: [Name, Role]}
  contexts:
    web:
      place: web::signed-out::sign-in
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#resolve_user
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#callback
---

# Sign in with single sign-on

## Trigger

A person who is not signed in opens Horae on an installation configured for OpenID Connect.

## Outcome

The person is signed in to their own account and arrives at the timesheet for the current week.

## Edge cases

- A provider error, a mismatched state or an unverifiable token returns the person to the sign-in page without a session.
