---
{
  "relations": [
    {
      "entity": "user",
      "verb": "identifies",
      "cardinality": "one-to-one"
    },
    {
      "entity": "private-motion-note",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "private-amendment-note",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "notification-settings",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "access-request",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "membership",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "vote",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "procedure-note",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "supporter",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "motion-comment",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "amendment-comment",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "user",
      "verb": "is challenged by",
      "cardinality": "one-to-many"
    },
    {
      "entity": "visitor",
      "verb": "challenges",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    }
  ]
}
---

# Account

Account information kept by Antragsgrün.

## Information kept

- **Name** — Personal display name.
- **Email** — Contact and confirmation destination.
- **Organization** — Personal organization information.
- **Authentication identity** — Identity and authentication method used to sign in.
- **Email confirmation** — Whether the address has been confirmed.
- **Password configuration** — Password, required-change configuration and pending recovery proof/timing, without disclosure of password or recovery-secret contents.
- **Second-factor configuration** — Enrolled keys and required-enrollment configuration without disclosure of secrets.
- **Account restrictions** — Fixed data, account constraints and controls on personal changes.
- **Vote weights** — Consultation-specific voting weights.
- **Pending email change** — Requested replacement address and confirmation timing.
- **Preferred language** — Chosen interface language.

## States

### Unconfirmed

Email confirmation is pending.

### Confirmed

Email confirmation is complete.

### Deactivated

The account has been deactivated.
