---
{
  "domain": "documents",
  "relations": [
    {
      "entity": "document",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationFileGroup.php"
    }
  ]
}
---

# Document group

Document group information kept by Antragsgrün.

## Information kept

- **Name** — Group title.
- **Order** — Group order.
- **Container** — Applicable consultation or page.
