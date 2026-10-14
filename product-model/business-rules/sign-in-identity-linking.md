---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts:
  - Sign-in identity
permits:
- related:
  - {verb: has, entity: member}
- related:
  - {verb: has, entity: manager}
- related:
  - {verb: has, entity: admin}
references:
- kind: code
  role: implementation
  target: crates/horae/src/auth/oidc.rs#resolve_user
---

# Only its own person links a sign-in identity to an account

An account's sign-in identity is linked only by that person completing single sign-on; nobody links an identity to someone else's account.
