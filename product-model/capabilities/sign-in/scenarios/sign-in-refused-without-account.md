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
- text: No account is linked to the identity and no unlinked account has its verified email
  kind: condition
  actor: member
  entities:
  - {entity: account, effect: reads, facts: [Sign-in identity, Email]}
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

# Sign in refused without a matching account

## Trigger

A person completes single sign-on with an identity that no account is linked to, and whose verified email matches no unlinked account.

## Outcome

The person stays signed out on the sign-in page.
