---
{
  "domain": "user-accounts",
  "relations": [
    {
      "entity": "membership",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "permission-entry",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "organization",
      "verb": "assigns",
      "cardinality": "many-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationUserGroup.php"
    }
  ]
}
---

# User group

User group information kept by Antragsgrün.

## Information kept

- **Name** — Group name.
- **Scope** — Applicable site or consultation container.
- **Template** — Template and editability configuration.
- **Selectability** — Whether available for ordinary membership selection.
- **Permissions** — Configured privilege entries.
