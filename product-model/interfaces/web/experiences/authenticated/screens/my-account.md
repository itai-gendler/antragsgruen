---
{
  "entities": [
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
        "Name",
        "Organization",
        "Password configuration",
        "Second-factor configuration",
        "Pending email change"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    }
  ]
}
---

# My account

Personal profile, authentication settings and account restrictions.
