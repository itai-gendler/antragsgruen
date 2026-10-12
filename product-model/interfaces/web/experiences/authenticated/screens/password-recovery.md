---
{
  "entities": [
    {
      "entity": "visitor",
      "shows": [
        "Anonymous continuity",
        "Preferred language",
        "Pending authentication"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Name",
        "Email",
        "Organization",
        "Authentication identity",
        "Email confirmation",
        "Password configuration",
        "Second-factor configuration",
        "Account restrictions",
        "Vote weights",
        "Pending email change",
        "Preferred language"
      ],
      "collects": [
        "Email"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    }
  ]
}
---

# Password recovery

Email/link/code/password recovery process and repeat requests.
