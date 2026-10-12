---
{
  "domain": "consultations",
  "relations": [
    {
      "entity": "consultation",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "user-group",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "page",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Site.php"
    }
  ]
}
---

# Site

Site information kept by Antragsgrün.

## Information kept

- **Identity** — The site's name and address.
- **Default consultation** — The consultation selected by default.
- **Access settings** — Site login and access configuration.
- **Deleted** — Whether the site is deleted.
