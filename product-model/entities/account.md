---
domain: user-management
relations:
- entity: team-membership
  verb: holds
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crates/horae/migrations/0001_init.sql
- kind: code
  role: implementation
  target: crates/horae/src/server_fns/users.rs
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#resolve_identity
---

# Account

A person's account in the organization, whatever their role. It carries who they are and
whether they may still sign in; their time stays with it when it is deactivated.

## Information kept

- **Name** — the person's display name, shown on timesheets, approvals and reports
- **Email** — the address the person is known by; unique across the installation
- **Role** — Member, Manager or Admin
- **Sign-in identity** — the identity-provider subject linked to the account at its first single sign-on

## States

### Active

The person can sign in and track time.

### Deactivated

The person can no longer sign in; their tracked time is kept.
