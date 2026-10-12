---
{
  "entities": [
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
    },
    {
      "entity": "access-request",
      "shows": [
        "Account",
        "Consultation",
        "Request information"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Consultation.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/UsersController.php"
    }
  ]
}
---

# Consultation access

Consultation access/request state and pending request.
