---
actors:
- member
- manager
- admin
access: authenticated
entryPoints:
- web: /timesheet/week
references:
- kind: code
  role: implementation
  target: crates/horae/src/route.rs#Route
- kind: code
  role: implementation
  target: crates/horae/src/components/sidebar.rs
---

# Team workspace

Everyone signed in tracks and submits their own time here. Managers and admins also review
submitted weeks, run reports and invoice clients from the same workspace.
