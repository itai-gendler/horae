---
availability:
- {place: 'web::team'}
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/budgets.rs#enqueue_alerts
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/budgets.rs#sweep
- kind: code
  role: implementation
  target: crates/horae/src/notifications.rs
- kind: code
  role: implementation
  target: crates/horae/src/scheduler.rs
---

# Send budget alert

The Product emails the people who follow a project when its spending reaches the budget alert threshold. It exists only while the deployment configures a mail program for budget alerts.
