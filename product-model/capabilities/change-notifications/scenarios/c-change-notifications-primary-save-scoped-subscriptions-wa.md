---
{
  "kind": "primary",
  "routes": {
    "route": "WA Save scoped subscriptions"
  },
  "steps": [
    {
      "text": "Change notifications request: Save scoped subscriptions.",
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
      "text": "Scoped event and comment notification selections are stored.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "notification-settings",
          "effect": "changes",
          "facts": [
            "Scope",
            "Event selections",
            "Comment preferences"
          ]
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

# Change notifications — Save scoped subscriptions — WA

## Trigger

Change notifications request: Save scoped subscriptions.

## Outcome

Scoped event and comment notification selections are stored.
