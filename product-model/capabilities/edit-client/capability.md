---
domain: clients
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#update_client_profile
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#update_client_record
---

# Edit client

A manager or admin changes a client's name, currency, default rate or billing address.
