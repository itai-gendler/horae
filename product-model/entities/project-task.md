---
domain: projects
relations:
- entity: time-entry
  verb: records
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crates/horae/migrations/0034_task_tracking_access.sql
- kind: code
  role: implementation
  target: crates/horae/src/models/project_creation.rs#ProjectTaskInput
---

# Project task

A task offered on one project, with how time on it bills there and who may track on it.

## Information kept

- **Billable** — whether time on the task is billable on this project
- **Hourly rate** — the task's rate on this project, when the project bills by task rate
- **Budget** — the task's share of the budget, when the project budgets per task
- **Access** — everyone on the project, or only selected people
- **Selected people** — who may track on the task when access is limited

## States

### Active

People can track time on the task in this project.

### Archived

The task is archived on this project and takes no new time there.
