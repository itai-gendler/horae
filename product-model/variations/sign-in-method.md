---
kind: configuration
of: capability-scenario
takesEffect: When the server starts; changing the deployment's sign-in configuration takes effect after a restart.
stability: Fixed for the life of the running server. Existing sessions are kept across a change of method.
alternatives:
- id: sign-in-with-sso
  selectedWhen: The development login is off and all four OpenID Connect settings (issuer, client id, client secret and redirect URL) are configured.
- id: sign-in-as-development-admin
  selectedWhen: The deployment enables the development login, whatever OpenID Connect settings are present.
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth.rs#router
- kind: code
  role: implementation
  target: crates/horae/src/config.rs
- kind: doc
  role: intent
  target: README.md
---

# Sign-in method

Production installations sign people in through the organization's OpenID Connect provider;
development and demo installations offer a one-click admin login instead. Both are
supported, and the deployment's configuration picks one.
