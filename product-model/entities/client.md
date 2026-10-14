---
domain: clients
relations:
- entity: project
  verb: has
  cardinality: one-to-many
- entity: invoice
  verb: is billed
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crates/horae/migrations/0001_init.sql
- kind: code
  role: implementation
  target: crates/horae/src/models/client.rs
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/clients.rs
---

# Client

A customer the organization does work for and invoices.

## Information kept

- **Name** — the client's name
- **Currency** — the currency the client is billed in
- **Billing address** — the address printed on the client's invoices
- **Default rate** — the hourly rate the client's work is billed at unless a project or task sets another

## States

### Active

The client's projects can be tracked on and invoiced.

### Inactive

The client is deactivated; its projects take no new time and it is offered for no new project or invoice.
