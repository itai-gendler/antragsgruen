---
{
  "kind": "primary",
  "routes": {
    "route": "WP Ordinary"
  },
  "steps": [
    {
      "text": "Sign in request: Ordinary.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "visitor",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::sign-in"
        }
      }
    },
    {
      "text": "Credential verification establishes the target Account session and returns to the requested destination.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "user",
          "effect": "changes",
          "facts": [
            "Session context"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Authentication identity"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::sign-in"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php#actionLogin"
    }
  ]
}
---

# Sign in — Ordinary — WP

## Trigger

Sign in request: Ordinary.

## Outcome

Credential verification establishes the target Account session and returns to the requested destination.
