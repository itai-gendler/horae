---
kind: primary
routes:
  web: Web
steps:
- text: The Manager chooses New Invoice, picks a client, a period and optionally some of its projects, and chooses Prepare invoice
  kind: actor
  actor: manager
  entities:
  - {entity: client, effect: reads, facts: [Name]}
  - {entity: invoice, effect: reads, facts: []}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::invoices
- text: The Product shows the billable time and fees the draft would bill
  kind: product
  actor: manager
  entities:
  - {entity: project, effect: reads, facts: [Fee balance]}
  contexts:
    web:
      place: web::team::invoices
- text: The Manager chooses Generate draft
  kind: actor
  actor: manager
  entities: []
  contexts:
    web:
      place: web::team::invoices
- text: The Product creates a draft invoice whose lines bill the period's open and approved billable time
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: creates, to: Draft, facts: [Number, Period, Issue date, Due date, Lines, Payment terms, Purchase order, Discount and taxes, Total]}
  contexts:
    web:
      place: web::team::invoices
- text: The Product marks the billed open time entries invoiced, freezing their rounded durations
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, as: open-time, effect: changes, from: Open, to: Invoiced, facts: [Rounded duration]}
  contexts:
    web:
      place: web::team::invoices
- text: The Product marks the billed approved time entries invoiced, freezing their rounded durations
  kind: product
  actor: manager
  entities:
  - {entity: time-entry, as: approved-time, effect: changes, from: Approved, to: Invoiced, facts: [Rounded duration]}
  contexts:
    web:
      place: web::team::invoices
- text: The Product opens the new invoice
  kind: product
  actor: manager
  entities:
  - {entity: invoice, effect: reads, facts: [Number]}
  contexts:
    web:
      place: web::team::invoice
---

# Generate an invoice from tracked time

## Trigger

A manager chooses New Invoice, picks a client, a period and optionally some of the client's projects, and generates it.

## Outcome

A draft invoice bills the period's open and approved billable time, that time is invoiced, and the manager lands on the new invoice.

## Edge cases

- Submitted time and running timers are not billed.
- Fixed-fee and retainer projects set up in the project editor bill through their fees rather than their time.
- Time already on another invoice is never billed twice.
