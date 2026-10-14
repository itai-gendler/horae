---
appliesTo:
- type: capability
  id: send-budget-alert
- type: entity
  id: budget-alert
  facts:
  - Threshold
  - Period
  - Recipient
references:
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/budgets.rs#enqueue_alerts
- kind: doc
  role: intent
  target: README.md
---

# A budget alert goes out once per person, threshold and period

Each person following a project gets at most one alert for each threshold in each budget period; delivery is attempted at most five times.
