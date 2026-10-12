---
{
  "domain": "motion-types",
  "relations": [
    {
      "entity": "section-definition",
      "verb": "classifies",
      "cardinality": "one-to-many"
    },
    {
      "entity": "motion",
      "verb": "classifies",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationMotionType.php"
    }
  ]
}
---

# Motion type

Motion type information kept by Antragsgrün.

## Information kept

- **Names** — Type titles and names.
- **Participation policies** — Configured creation, support, comment and voting policies.
- **Deadlines** — Creation, editing, support and merge deadlines, including child-amendment deadlines.
- **Support thresholds** — Ordinary and female-supporter thresholds.
- **Screening** — Submission and comment screening configuration.
- **Amendment settings** — Amendment, resolution, child-amendment and initiator merge configuration.
- **Flags** — Text editability, fixed text and related type behavior.
- **Deleted** — Whether the type is deleted.
