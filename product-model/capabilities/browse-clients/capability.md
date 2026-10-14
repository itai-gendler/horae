---
domain: clients
availability:
- {place: 'web::team'}
- {place: harvest-api}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#client_overview
- kind: code
  role: implementation
  target: crates/horae/src/pages/clients.rs#ClientList
- kind: code
  role: implementation
  target: crates/horae/src/harvest/client_reads.rs
---

# Browse clients

A person looks through the organization's clients, by name, status and currency, in the web application or through the Harvest-style API.
