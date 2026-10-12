---
{
  "acts": "external",
  "kind": "person",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php"
    }
  ]
}
---

# User

An authenticated person using a Web session or the Antragsgrün API.

## Information kept

- **Session context** — The current authenticated acting identity and session.
- **Pending authentication** — An account-switch challenge may target a different account from the current authenticated account.
