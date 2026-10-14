---
domain: invoices
relations:
- entity: time-entry
  verb: bills
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crates/horae/src/models/invoice.rs
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/invoices.rs
---

# Invoice

A bill to one client for the billable time and fees of a period.

## Information kept

- **Number** — the invoice number, unique in the organization
- **Period** — the dates whose time the invoice bills
- **Issue date** — the day the invoice is issued
- **Due date** — the day payment is due
- **Lines** — the billed time and fee lines with their hours, rates and amounts
- **Payment terms** — how many days the client has to pay
- **Purchase order** — the client's purchase order number, when given
- **Discount and taxes** — the discount and up to two taxes applied to the subtotal
- **Total** — the amount due, after discount and taxes

## States

### Draft

The invoice has been generated and can still change.

### Sent

The invoice has been sent to the client.

### Paid

The client has paid the invoice.

### Void

The invoice was cancelled; its time is open again.
