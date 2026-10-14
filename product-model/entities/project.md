---
domain: projects
relations:
- entity: project-task
  verb: has
  cardinality: one-to-many
- entity: team-membership
  verb: has
  cardinality: one-to-many
- entity: budget-alert
  verb: raises
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crates/horae/migrations/0001_init.sql
- kind: code
  role: implementation
  target: crates/horae/src/models/project.rs
- kind: code
  role: implementation
  target: crates/horae/src/models/project_creation.rs#ProjectForm
---

# Project

A piece of work for one client that people track time on, with how it bills and what it may cost.

## Information kept

- **Name** — the project's name
- **Code** — a short code that identifies the project
- **Dates** — advisory start and end dates; they do not limit tracking
- **Tags** — labels used to group and filter projects
- **Notes** — private context for the people who manage the project
- **Currency** — the currency the project bills in
- **Project type** — time and materials, fixed fee, non-billable or retainer
- **Billing rates** — how billable hours are priced: one project rate, each task's rate, or each person's rate
- **Budget** — no budget, or hours or fees for the whole project, per task or per person, optionally resetting every month and optionally counting non-billable time
- **Budget alert** — whether an email goes out when spending reaches a chosen percentage of the budget
- **Fees** — for fixed-fee and retainer projects, a single fee, milestones with due dates, or a monthly fee
- **Invoice defaults** — payment terms, purchase order, taxes and discount used when invoicing the project
- **Report visibility** — whether everyone on the project or only its project managers see its budget progress
- **Budget progress** — time and money spent against the budget so far
- **Fee balance** — how much of the project's fees has been invoiced and how much remains

## States

### Active

Time can be tracked on the project.

### Archived

The project takes no new time; its tracked time stays in timesheets, reports and invoices.
