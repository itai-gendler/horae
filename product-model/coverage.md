---
scope: The Horae application crate, its pure domain crate and its database migrations.
method: Static inspection of source, migrations, tests and specifications at b675d96; nothing executed.
covered:
- description: Time entry, timesheet and timer server functions, pages and sidebar timer.
  paths:
  - crates/horae/src/server_fns/time_entries.rs
  - crates/horae/src/server_fns/time_entries/
  - crates/horae/src/pages/timesheet.rs
  - crates/horae/src/pages/timesheet/
  - crates/horae/src/components/timer_widget.rs
  - crates/horae/src/models/time_entry.rs
  - crates/horae/src/models/scoped_time.rs
- description: Week submission and approval server functions and page.
  paths:
  - crates/horae/src/server_fns/approvals.rs
  - crates/horae/src/pages/approvals.rs
  - crates/horae/src/models/approval.rs
- description: Domain arithmetic and state machines for time, money, budgets, clients, projects and invoices.
  paths:
  - crates/core/src/state.rs
  - crates/core/src/types.rs
  - crates/core/src/duration.rs
  - crates/core/src/rounding.rs
  - crates/core/src/time_of_day.rs
  - crates/core/src/week.rs
  - crates/core/src/totals.rs
  - crates/core/src/money.rs
  - crates/core/src/decimal.rs
  - crates/core/src/budget.rs
  - crates/core/src/client.rs
  - crates/core/src/project.rs
  - crates/core/src/invoice.rs
  - crates/core/src/importers.rs
  - crates/core/src/importers/
- description: Sign-in, sessions and the login redirect.
  paths:
  - crates/horae/src/auth.rs
  - crates/horae/src/auth/
  - crates/horae/src/server_fns/auth.rs
  - crates/horae/src/pages/auth.rs
- description: Account administration, the task list on User Management and the user directory.
  paths:
  - crates/horae/src/server_fns/users.rs
  - crates/horae/src/server_fns/users/
  - crates/horae/src/pages/admin.rs
  - crates/horae/src/models/user.rs
  - crates/horae/src/models/people.rs
- description: Client server functions and pages.
  paths:
  - crates/horae/src/server_fns/clients.rs
  - crates/horae/src/server_fns/clients/
  - crates/horae/src/pages/clients.rs
  - crates/horae/src/pages/clients/
  - crates/horae/src/models/client.rs
- description: Project, project task, team and project creation and editing server functions and pages.
  paths:
  - crates/horae/src/server_fns/projects.rs
  - crates/horae/src/server_fns/projects/
  - crates/horae/src/server_fns/project_creation.rs
  - crates/horae/src/server_fns/project_creation/
  - crates/horae/src/server_fns/project_managers.rs
  - crates/horae/src/pages/projects.rs
  - crates/horae/src/pages/projects/
  - crates/horae/src/pages/new_project.rs
  - crates/horae/src/pages/new_project/
  - crates/horae/src/models/project.rs
  - crates/horae/src/models/project_creation.rs
  - crates/horae/src/models/project_managers.rs
  - crates/horae/src/models/project_people.rs
  - crates/horae/src/models/task.rs
  - crates/horae/src/models/assignment.rs
  - crates/horae/src/components/project_task_picker.rs
- description: Budget evaluation, budget-alert mail and the background scheduler.
  paths:
  - crates/horae/src/server_fns/budgets.rs
  - crates/horae/src/notifications.rs
  - crates/horae/src/notifications/
  - crates/horae/src/scheduler.rs
- description: Time reports, project and invoice exports.
  paths:
  - crates/horae/src/server_fns/reports.rs
  - crates/horae/src/reports.rs
  - crates/horae/src/reports/
  - crates/horae/src/pages/reports.rs
  - crates/horae/src/pages/reports/
  - crates/horae/src/models/time_report.rs
  - crates/horae/src/render.rs
  - crates/horae/templates/
- description: Invoice preparation, generation, editing, fees and status transitions.
  paths:
  - crates/horae/src/server_fns/invoices.rs
  - crates/horae/src/server_fns/invoices/
  - crates/horae/src/pages/invoices.rs
  - crates/horae/src/pages/invoices/
  - crates/horae/src/models/invoice.rs
- description: Harvest-style read API.
  paths:
  - crates/horae/src/harvest/
- description: Harvest importer, durable import jobs and the remote import commands.
  paths:
  - crates/horae/src/importers.rs
  - crates/horae/src/importers/
  - crates/horae/src/jobs.rs
  - crates/horae/src/jobs/
  - crates/horae/src/server_fns/importers.rs
  - crates/horae/src/server_fns/importers/
  - crates/horae/src/pages/importers.rs
  - crates/horae/src/pages/importers/
  - crates/horae/src/cli/
  - crates/horae/src/models/jobs.rs
- description: Command-line bootstrap, user commands and startup configuration.
  paths:
  - crates/horae/src/cli.rs
  - crates/horae/src/init.rs
  - crates/horae/src/main.rs
  - crates/horae/src/config.rs
  - crates/horae/src/config/
- description: Database schema and eligibility and visibility views.
  paths:
  - crates/horae/migrations/
- description: Routes and navigation shells.
  paths:
  - crates/horae/src/route.rs
  - crates/horae/src/components/sidebar.rs
  - crates/horae/src/components/layout.rs
  - crates/horae/src/components/admin_shell.rs
exclusions:
- description: 'Scoped permission profiles, templates, management assignments, permission editor, audit log and task catalog page: inactive, because no shipped command or page switches an organization to the scoped permission policy.'
  paths:
  - crates/horae/src/server_fns/permissions.rs
  - crates/horae/src/server_fns/permissions/
  - crates/horae/src/server_fns/permission_editor.rs
  - crates/horae/src/pages/admin/
  - crates/horae/src/pages/permission_audit.rs
  - crates/horae/src/pages/settings/
  - crates/horae/src/pages/tasks.rs
  - crates/horae/src/pages/tasks/
  - crates/core/src/permissions.rs
  - crates/core/src/permissions/
  - crates/horae/src/models/permissions.rs
  - crates/horae/src/models/permission_editor.rs
  - crates/horae/src/models/permission_audit.rs
  - crates/horae/src/models/own_permissions.rs
  - crates/horae/migrations/0042_scoped_permission_state.sql
- description: 'Plugin host, plugin events and plugin widgets: an extension point whose behavior belongs to operator-installed plugins.'
  paths:
  - crates/horae/src/plugin/
  - crates/horae/src/server_fns/plugins.rs
  - crates/test-plugins/
- description: 'Demo seed: sample data for trying the product, not product behavior.'
  paths:
  - crates/horae/src/seed.rs
  - crates/horae/src/seed/
  - crates/horae/src/server_fns/test_seed.rs
- description: 'Settings page appearance choice and organization branding functions: a device-local theme and branding with no page that edits it.'
  paths:
  - crates/horae/src/pages/settings.rs
  - crates/horae/src/components/theme.rs
  - crates/horae/src/server_fns/organization.rs
  - crates/horae/src/models/organization.rs
- description: Design system, styling, shared UI widgets and the component gallery.
  paths:
  - crates/horae/assets/
  - design/
  - DESIGN.md
  - crates/horae/src/pages/gallery.rs
  - crates/horae/src/components/
- description: Build, packaging, development environment, database tooling and CI.
  paths:
  - nix/
  - flake.nix
  - flake.lock
  - process-compose.yaml
  - .github/
  - vendor/
  - Cargo.toml
  - Cargo.lock
  - crates/horae/src/db.rs
  - crates/horae/src/state.rs
  - crates/horae/src/error.rs
  - crates/horae/src/app.rs
- description: Compile-time query cache.
  paths:
  - .sqlx/
- description: Agent and spec-tooling configuration.
  paths:
  - .agents/
  - .specify/
  - .claude/
- description: Test suites.
  paths:
  - crates/horae/tests/
unmapped: []
limitations: []
---

# Coverage
