---
id: horae
summary: 'Self-hostable team time tracking: log hours against clients, projects and tasks, submit weeks for approval, manage project budgets, report on time and invoice it.'
category: time-tracking
tags:
- time-tracking
- timesheets
- approvals
- invoicing
- self-hosted
authors:
- name: The Horae authors
  url: https://github.com/numtide/horae
license: MIT
languages:
- en
limitations:
- Each installation serves exactly one organization.
- People sign in through the organization's own OpenID Connect provider; Horae keeps no passwords.
- Time is submitted and approved a whole week at a time, never entry by entry.
- The Harvest-style API only reads; every change happens in the web application.
- Durations are kept in whole minutes.
references:
- kind: doc
  role: intent
  target: README.md
- kind: spec
  role: intent
  target: specs/001-time-tracking-invoicing/spec.md
- kind: doc
  role: context
  target: PLAN.md
---

# Horae

Horae is a time tracker a team runs on its own infrastructure. People log the hours they
work against clients, projects and tasks, either by running a timer or by typing a
duration, and see their time on a day, week or calendar timesheet. At the end of a week
each person submits it for approval; managers and admins approve it or reopen it.

Managers and admins keep the clients and projects time is tracked on: how each project
bills, its budget and alerts, which tasks it offers and who is on its team. They report on
the organization's time, export it, and turn billable time and fees into invoices. Admins
manage the organization's people and can bring an existing Harvest account's data in. A
read-only, Harvest-shaped API lets integrations read the same data.

## Intent

The README presents Horae as "a Harvest / Kimai alternative that stays fully yours": a
time tracker you run yourself, so you can "log hours against clients and projects, submit
and approve timesheets, and export billable reports — without handing your data to a SaaS
vendor." Correctness of the numbers is a stated priority: durations, rounding, money and
timesheet totals are kept exact, in whole minutes and minor currency units.
