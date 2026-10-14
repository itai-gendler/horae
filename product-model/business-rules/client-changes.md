---
appliesTo:
- type: entity
  id: client
  effect: changes
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#update_client_profile
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#set_client_active
---

# Only managers and admins change or deactivate a client

Editing, deactivating and activating clients is reserved to managers and admins.
