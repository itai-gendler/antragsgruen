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
      ],
      "collects": [
        "Name",
        "Email"
      ]
    },
    {
      "entity": "site",
      "shows": [
        "Identity",
        "Default consultation",
        "Access settings",
        "Deleted"
      ]
    },
    {
      "entity": "consultation",
      "shows": [
        "Title",
        "Language",
        "Participation settings",
        "Display settings",
        "Wording base",
        "Lifecycle dates",
        "Deleted",
        "Public API"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Site.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Consultation.php"
    }
  ]
}
---

# Sign-in

Registration/sign-in, pending challenge, required password change or enrollment, and consultation-password process.
