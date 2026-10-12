---
{
  "domain": "voting",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Vote.php"
    }
  ]
}
---

# Vote

Vote information kept by Antragsgrün.

## Information kept

- **Account** — Voting account.
- **Voting and item** — Ballot, question or document item.
- **Answer** — Recorded answer.
- **Weight** — Server-selected weight.
- **Time** — Time the vote was cast.
- **Retained publicity** — Publicity retained for this vote.
