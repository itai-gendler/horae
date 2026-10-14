---
kind: validation
routes:
  web: Web
steps:
- text: The Member opens Reports
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::reports
- text: The Product refuses the report
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::team::reports
references:
- kind: code
  role: implementation
  target: crates/horae/src/reports/limits/time.rs#authorize_current
---

# Reports are closed to members

## Trigger

A member opens Reports.

## Outcome

No report is shown.
