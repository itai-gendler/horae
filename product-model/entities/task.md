---
relations:
- entity: project-task
  verb: is offered as
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crates/horae/migrations/0001_init.sql
- kind: code
  role: implementation
  target: crates/horae/src/models/task.rs
---

# Task

A kind of work, such as design or development, that projects offer for tracking.

## Information kept

- **Name** — the task's name
- **Billable by default** — whether the task is billable on a project unless the project says otherwise
- **Archived** — whether the task is archived in the task catalog; an archived task takes no new time
