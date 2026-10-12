---
{
  "domain": "consultation-settings",
  "relations": [
    {
      "entity": "motion-type",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "agenda-item",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "tag",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "motion",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "page",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "document-group",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "user-group",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "voting",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "speaking-list",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "debate",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "organization",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "wording-override",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "activity-entry",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "access-request",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Consultation.php"
    }
  ]
}
---

# Consultation

Consultation information kept by Antragsgrün.

## Information kept

- **Title** — Consultation title and address.
- **Language** — Consultation language.
- **Participation settings** — Access, password, forced-login, managed membership and allowed authentication-method configuration.
- **Display settings** — Behavioral display, speaking and private-note settings.
- **Wording base** — Selected base wording.
- **Lifecycle dates** — Relevant consultation dates.
- **Deleted** — Whether the consultation is deleted.
- **Public API** — Whether ordinary public API access is enabled.
