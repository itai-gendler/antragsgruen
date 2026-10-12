---
{
  "kind": "validation",
  "routes": {
    "route": "WA Scope/input refused"
  },
  "steps": [
    {
      "text": "Change notifications request: Scope/input refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "notification-settings",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::notifications"
        }
      }
    },
    {
      "text": "Scope or submitted selections are invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "notification-settings",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::notifications"
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

# Change notifications — Scope/input refused — WA

## Trigger

Change notifications request: Scope/input refused.

## Outcome

Scope or submitted selections are invalid. This attempt does not complete the requested operation.
