---
{
  "domain": "voting",
  "relations": [
    {
      "entity": "voting-question",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "vote",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "voting-activity",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "motion",
      "verb": "includes",
      "cardinality": "one-to-many"
    },
    {
      "entity": "amendment",
      "verb": "includes",
      "cardinality": "one-to-many"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/VotingBlock.php"
    }
  ]
}
---

# Voting

Voting information kept by Antragsgrün.

## Information kept

- **Title** — Voting title.
- **Phase** — Offline, preparing, open, closed-unpublished or closed-published.
- **Order** — Ballot and item ordering.
- **Assignments** — Document and debate associations.
- **Answers** — Configured answers.
- **Majority and quorum** — Majority type (simple, absolute or two-thirds) and quorum type.
- **Participation policy** — Voting participation configuration.
- **Limits** — Applicable group and default voting limits.
- **Publicity** — Current result and individual-vote disclosure configuration.
- **Opening snapshot** — Publicity retained at first opening.
