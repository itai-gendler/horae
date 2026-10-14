---
appliesTo:
- type: entity
  id: account
  effect: reads
  contexts:
  - {place: 'web::administration::user-management'}
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs#list_users
---

# Only admins see deactivated accounts in User Management

Any signed-in person may list active people; the full list with deactivated accounts is for admins.
