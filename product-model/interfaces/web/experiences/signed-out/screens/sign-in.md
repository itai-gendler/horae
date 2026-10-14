---
entryPoints:
- web: /auth/login
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth/page.rs
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#login_page
- kind: code
  role: implementation
  target: crates/horae/src/auth/dev.rs#login_page
---

# Sign in

Where a person signs in to Horae.
