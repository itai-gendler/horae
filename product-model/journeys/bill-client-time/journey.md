---
actors:
- manager
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/invoices.rs#InvoiceList
- kind: code
  role: implementation
  target: crates/horae/src/pages/invoices.rs#InvoiceDetail
---

# Bill a client's time

## Goal

A manager turns a client's billable time for a period into an invoice and sends it.

## Success criterion

The client has a sent invoice whose lines bill the period's open and approved billable time.
