---
domain: user-management
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#set_user_active
---

# Activate user

An admin lets a deactivated person sign in again.
