---
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/budgets.rs#enqueue_alerts
- kind: code
  role: implementation
  target: crates/horae/src/notifications.rs
- kind: doc
  role: intent
  target: README.md
---

# Budget alert

An email telling one person that a project's budget reached its alert threshold in a period.

## Information kept

- **Threshold** — the percentage of the budget that was reached
- **Period** — the budget period it was reached in: the whole project or one month
- **Recipient** — who the alert is for

## States

### Pending

The alert waits to be handed to the mail program.

### Delivered

The mail program accepted the alert.

### Failed

Delivery stopped after its attempts ran out or the recipient was no longer eligible.
