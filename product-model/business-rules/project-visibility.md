---
appliesTo:
- type: entity
  id: project
  effect: reads
  contexts:
  - {place: 'web::team::projects'}
  - {place: 'web::team::project'}
permits:
- actors:
  - manager
  - admin
- related:
  - {verb: has, entity: team-membership}
  - {verb: holds, entity: account}
  - {verb: has, entity: member}
- related:
  - {verb: has, entity: project-task}
  - {verb: records, entity: time-entry}
  - {verb: owns, entity: member}
- unattended: true
references:
- kind: code
  role: implementation
  target: crates/horae/migrations/0035_project_read_access.sql
---

# Members see only the projects they are on or have tracked time on

Managers and admins see every project; anyone else sees a project when they are on its team or have tracked time on it.
