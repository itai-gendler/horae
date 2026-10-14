---
actors:
- admin
access: restricted
entryPoints:
- web: /admin/users
references:
- kind: code
  role: implementation
  target: crates/horae/src/route.rs#Route
- kind: code
  role: implementation
  target: crates/horae/src/pages/admin.rs#AdminUsers
---

# Administration

The area where admins manage the organization's people and their roles.
