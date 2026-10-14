---
appliesTo:
- type: entity
  id: project
  effect: reads
  facts:
  - Budget progress
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: has, entity: team-membership}
  - {verb: holds, entity: account}
  - {verb: has, entity: member}
  when:
  - {entity: team-membership, fact: Project role, is: Project manager}
- related:
  - {verb: has, entity: team-membership}
  - {verb: holds, entity: account}
  - {verb: has, entity: member}
  when:
  - {fact: Report visibility, is: Everyone on the project}
- unattended: true
references:
- kind: code
  role: implementation
  target: crates/horae/migrations/0035_project_read_access.sql
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/projects.rs#list_project_budget_progress
---

# Budget progress is shown to managers, admins, the project's managers, and its team when the project allows

A project's budget progress is visible to managers and admins, to its project managers, and to everyone on its team when its report visibility is everyone on the project.
