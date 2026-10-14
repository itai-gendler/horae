---
domain: clients
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#set_client_active
---

# Deactivate client

A manager or admin deactivates a client, stopping new work for it while keeping its history.
