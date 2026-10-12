---
{
  "domain": "pages",
  "relations": [
    {
      "entity": "document-group",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    }
  ]
}
---

# Page

Page information kept by Antragsgrün.

## Information kept

- **Address** — Addressed page slug.
- **Title** — Displayed title.
- **Contents** — Page contents.
- **Scope** — Consultation, site or installation-wide scope.
- **Menu inclusion** — Whether included as configured.
- **Read policy** — Configured read policy.
- **Editing information** — Recorded editing information.
- **Files** — Associated file group.
