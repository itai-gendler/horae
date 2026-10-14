---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters a task name, chooses whether it is billable by default and chooses Create Task
  kind: actor
  actor: admin
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::administration::user-management
- text: The Product creates the task record
  kind: product
  actor: admin
  entities:
  - {entity: task, effect: creates, facts: [Name, Billable by default, Archived]}
  contexts:
    web:
      place: web::administration::user-management
---

# Create a task

## Trigger

An admin chooses Add Task in the Tasks section of User Management.

## Outcome

The task exists and can be offered on projects.
