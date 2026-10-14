---
domain: clients
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#client_detail_view
- kind: code
  role: implementation
  target: crates/horae/src/pages/clients/detail.rs
---

# View client

A person opens one client with its profile and projects; managers and admins also see its default rate and invoices.
