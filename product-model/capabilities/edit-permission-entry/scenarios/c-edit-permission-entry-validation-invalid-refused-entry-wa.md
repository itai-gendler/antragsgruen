---
{
  "kind": "validation",
  "routes": {
    "route": "WA Invalid/refused entry"
  },
  "steps": [
    {
      "text": "Edit permission entry request: Invalid/refused entry.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "permission-entry",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-group-administration"
        }
      }
    },
    {
      "text": "Privilege/restriction input is invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "permission-entry",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-group-administration"
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

# Edit permission entry — Invalid/refused entry — WA

## Trigger

Edit permission entry request: Invalid/refused entry.

## Outcome

Privilege/restriction input is invalid. This attempt does not complete the requested operation.
