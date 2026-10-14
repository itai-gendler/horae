---
appliesTo:
- type: capability
  id: sign-in
- type: capability
  id: deactivate-user
- type: entity
  id: account
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#resolve_identity
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#set_user_active
---

# Deactivated people cannot sign in, and their time is kept

A deactivated account is refused at sign-in and cannot track time; its time entries stay in timesheets, reports and invoices.
