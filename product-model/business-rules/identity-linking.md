---
appliesTo:
- type: capability-scenario
  id: sign-in-with-sso
- type: entity
  id: account
  facts:
  - Sign-in identity
  - Email
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#resolve_identity
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#fetch_unlinked_by_email
---

# A first single sign-on claims only an unlinked account with the same verified email

An identity already linked to an account always signs in to that account. An unlinked identity claims the active account with its verified email only while that account has no linked identity; an unverified email claims nothing.
