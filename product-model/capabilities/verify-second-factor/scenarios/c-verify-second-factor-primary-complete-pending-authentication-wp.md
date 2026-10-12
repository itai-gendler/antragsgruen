---
{
  "kind": "primary",
  "routes": {
    "route": "WP Complete pending authentication"
  },
  "steps": [
    {
      "text": "Verify second factor request: Complete pending authentication.",
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
      "text": "The pending target's factor proof completes its pending authentication.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "visitor",
          "effect": "changes",
          "facts": [
            "Pending authentication"
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
    }
  ]
}
---

# Verify second factor — Complete pending authentication — WP

## Trigger

Verify second factor request: Complete pending authentication.

## Outcome

The pending target's factor proof completes its pending authentication.
