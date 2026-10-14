---
availability:
- {place: 'web::signed-out'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth.rs#router
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#callback
- kind: code
  role: implementation
  target: crates/horae/src/auth/dev.rs#dev_login_post
---

# Sign in

A person signs in to Horae through the organization's identity provider, or, on a development installation, with one click as an admin.
