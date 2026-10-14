---
singleton: true
relations:
- entity: account
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: crates/horae/migrations/0001_init.sql
- kind: code
  role: implementation
  target: crates/horae/src/init.rs#run
---

# Organization

The one organization an installation serves, holding the settings every person's time is
measured by.

## Information kept

- **Name** — the organization's name
- **First day of the week** — the weekday every timesheet week starts on; Monday unless set otherwise
- **Rounding increment** — the number of minutes submitted and invoiced time is rounded to; none by default
- **Rounding direction** — whether rounding goes up, down or to the nearest increment; nearest by default
- **Default currency** — the currency money is kept in unless a client or project says otherwise
- **Long timer limit** — how long a timer may run before it counts as forgotten; eight hours by default
