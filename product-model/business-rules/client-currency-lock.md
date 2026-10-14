---
appliesTo:
- type: capability
  id: edit-client
- type: entity
  id: client
  facts:
  - Currency
  - Default rate
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs#update_client_record
---

# A client's currency stays fixed while it has a default rate

Changing the currency of a client with a default rate is refused; the default rate is kept in that currency.
