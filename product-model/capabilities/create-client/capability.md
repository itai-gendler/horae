---
domain: clients
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#create_client_profile
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#create_project_client
- kind: code
  role: implementation
  target: crates/horae/src/pages/clients/form.rs
---

# Create client

A manager or admin adds a client, from Clients or while setting up a new project.
