---
{
  "relations": [
    {
      "entity": "speaking-list",
      "verb": "attaches",
      "cardinality": "one-to-many"
    },
    {
      "entity": "voting",
      "verb": "attaches",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/DebateItem.php"
    }
  ]
}
---

# Debate

Debate information kept by Antragsgrün.

## Information kept

- **Target** — Selected Motion, Amendment, Agenda item or free text.
- **Start time** — When this debate started.
- **End time** — When this debate ended.
- **Attachments** — Speaking list and voting resources.
