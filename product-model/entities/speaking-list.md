---
{
  "domain": "speaking-lists",
  "relations": [
    {
      "entity": "speaking-subqueue",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "speech",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechQueue.php"
    }
  ]
}
---

# Speaking list

Speaking list information kept by Antragsgrün.

## Information kept

- **Target** — Associated document, agenda item or unassigned context.
- **Active** — Active-list setting.
- **Open flags** — Ordinary and point-of-order application gates.
- **Naming** — Login requirement, own-name and name-publicity settings.
- **Timing** — Speaking and application timing settings.
