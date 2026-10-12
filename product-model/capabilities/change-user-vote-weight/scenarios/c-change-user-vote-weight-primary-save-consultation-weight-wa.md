---
{
  "kind": "primary",
  "routes": {
    "route": "WA Save consultation weight"
  },
  "steps": [
    {
      "text": "Change user selected item weight request: Save selected item weight.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-account-administration"
        }
      }
    },
    {
      "text": "The account's consultation voting weight persists.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Vote weights"
          ]
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "voting",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-account-administration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/UsersController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/UserGroupPermissionEntry.php"
    }
  ]
}
---

# Change user vote weight — Save consultation weight — WA

## Trigger

Change user vote weight request: Save consultation weight.

## Outcome

The account's consultation vote weight persists.
