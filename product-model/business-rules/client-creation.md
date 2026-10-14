---
appliesTo:
- type: entity
  id: client
  effect: creates
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#create_client_profile
---

# Only managers and admins add clients

Clients are created by managers and admins, including from the project form and through imports.
