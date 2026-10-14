---
kind: alternative
routes:
  web: Web
steps:
- text: The Manager types a new task name and adds it
  kind: actor
  actor: manager
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
- text: The Product creates the task and offers it on the project
  kind: product
  actor: manager
  entities:
  - {entity: task, effect: creates, facts: [Name, Billable by default, Archived]}
  - {entity: project-task, effect: creates, to: Active, facts: [Billable, Hourly rate, Budget, Access, Selected people], with: task}
  - {entity: project, effect: reads, facts: []}
  contexts:
    web:
      place: web::team::project-settings
---

# Name a new task for a project

## Trigger

A manager types a task name that matches no existing task and adds it.

## Outcome

The new task exists for the organization and is offered on the project.
