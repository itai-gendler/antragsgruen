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
      "target": "models/db/AmendmentProposal.php"
    }
  ]
}
---

# Amendment proposed procedure

Amendment proposed procedure information kept by Antragsgrün.

## Information kept

- **Version** — Proposal version.
- **Recommendation** — Procedure status and reference.
- **Explanation** — Proposal explanation.
- **Visibility time** — Kept publication time.
- **Notification information** — Feedback request and notification information.
- **Proposer response** — Proposer acceptance or rejection.
- **Alternative text** — Direct proposed-change association.
- **Move destination** — Proposed move destination and reference.
- **Deleted** — Whether the version is deleted.
