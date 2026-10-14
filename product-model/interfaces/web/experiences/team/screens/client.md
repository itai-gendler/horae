---
entities:
- entity: client
  shows:
  - Name
  - Currency
  - Billing address
  - Default rate
- entity: project
  shows:
  - Name
  - Code
  - Budget progress
- entity: invoice
  shows:
  - Number
  - Issue date
  - Total
entryPoints:
- web: /clients/:id
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/clients/detail.rs
---

# Client

One client's profile with its projects and, for those who may see them, its invoices.
