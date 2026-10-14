---
actors:
- member
- manager
- admin
access: public
entryPoints:
- web: /auth/login
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth.rs#router
---

# Signed out

A person who is not signed in reaches only the sign-in page; every other page sends them
there.
