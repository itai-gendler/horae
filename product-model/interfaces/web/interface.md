---
type: web
actors:
- member
- manager
- admin
entryPoints:
- web: /timesheet/week
- web: /auth/login
references:
- kind: code
  role: implementation
  target: crates/horae/src/route.rs#Route
- kind: code
  role: implementation
  target: crates/horae/src/auth.rs#login_redirect_guard
- kind: doc
  role: intent
  target: README.md
---

# Web application

The browser application the team works in: the sign-in page, the timesheet, approvals,
reports and invoices, and the administration area.
