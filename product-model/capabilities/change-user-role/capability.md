---
domain: user-management
availability:
- {place: 'web::administration'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#set_user_role
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#change_user_role
---

# Change user role

An admin changes a person's role between Member, Manager and Admin.
