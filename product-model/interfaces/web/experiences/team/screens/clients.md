---
entities:
- entity: client
  shows:
  - Name
  - Currency
  - Default rate
  - Billing address
  collects:
  - Name
  - Currency
  - Default rate
  - Billing address
entryPoints:
- web: /clients
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/clients.rs#ClientList
- kind: code
  role: implementation
  target: crates/horae/src/pages/clients/form.rs
---

# Clients

The organization's clients, searchable and filtered by status and currency, and where a client
is added or edited.
