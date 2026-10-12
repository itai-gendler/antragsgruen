---
{
  "kind": "primary",
  "routes": {
    "route": "WA Set preference"
  },
  "steps": [
    {
      "text": "Change language request: Set preference.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation"
        }
      }
    },
    {
      "text": "The chosen interface language is retained in the Account preference.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Preferred language"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation"
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

# Change language — Set preference — WA

## Trigger

Change language request: Set preference.

## Outcome

The chosen interface language is retained in the Account preference.
