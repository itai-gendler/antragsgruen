---
{
  "kind": "primary",
  "routes": {
    "route": "WP Set preference"
  },
  "steps": [
    {
      "text": "Change language request: Set preference.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::public::consultation"
        }
      }
    },
    {
      "text": "The chosen interface language is retained for the Visitor through anonymous continuity.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "visitor",
          "effect": "changes",
          "facts": [
            "Preferred language"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::consultation"
        }
      }
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
      "target": "models/forms/LoginUsernamePasswordForm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/UserController.php"
    }
  ]
}
---

# Change language — Set preference — WP

## Trigger

Change language request: Set preference.

## Outcome

The chosen interface language is retained for the Visitor through anonymous continuity.
