---
{
  "kind": "validation",
  "routes": {
    "route": "WA Invalid/refused entry"
  },
  "steps": [
    {
      "text": "Add permission entry request: Invalid/refused entry.",
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
      "text": "Privilege is unknown, scope reference invalid, or a nonmotion privilege is restricted. This attempt does not complete the requested operation.",
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

# Add permission entry — Invalid/refused entry — WA

## Trigger

Add permission entry request: Invalid/refused entry.

## Outcome

Privilege is unknown, scope reference invalid, or a nonmotion privilege is restricted. This attempt does not complete the requested operation.
