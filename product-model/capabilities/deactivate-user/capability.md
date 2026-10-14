---
domain: user-management
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#set_user_active
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#change_user_active
---

# Deactivate user

An admin stops a person from signing in while keeping their time.
