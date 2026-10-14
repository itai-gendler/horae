---
appliesTo:
- type: entity
  id: client
  effect: reads
  facts:
  - Default rate
permits:
- actors:
  - manager
  - admin
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#client_details_in_scope
---

# Only managers and admins see a client's default rate

Everyone signed in sees clients; their default rate is shown only to managers and admins.
