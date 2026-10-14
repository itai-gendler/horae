---
entities:
- entity: time-entry
  shows:
  - Date
  - Duration
  - Rounded duration
  - Billable
  - Notes
- entity: project
  shows:
  - Name
- entity: task
  shows:
  - Name
- entity: client
  shows:
  - Name
- entity: account
  shows:
  - Name
entryPoints:
- web: /reports
references:
- kind: code
  role: implementation
  target: crates/horae/src/pages/reports.rs#Reports
---

# Reports

The organization's time for a chosen period, grouped by project, client, task or person
and narrowed by client, project, teammate or project tag.
