---
{
  "entities": [
    {
      "entity": "visitor",
      "shows": [
        "Preferred language"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Name",
        "Email confirmation"
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

# Email confirmation

Pending confirmation context, supplied code/captcha and resend.
