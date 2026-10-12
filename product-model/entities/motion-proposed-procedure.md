---
{
  "domain": "proposed-procedure",
  "relations": [
    {
      "entity": "proposed-change",
      "verb": "has",
      "cardinality": "one-to-one"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/MotionProposal.php"
    }
  ]
}
---

# Motion proposed procedure

Motion proposed procedure information kept by Antragsgrün.

## Information kept

- **Version** — Proposal version.
- **Recommendation** — Procedure status and reference.
- **Explanation** — Proposal explanation.
- **Visibility time** — Kept publication time.
- **Notification information** — Feedback request and notification information.
- **Proposer response** — Proposer acceptance or rejection.
- **Alternative text** — Direct proposed-change association.
- **Deleted** — Whether the version is deleted.
