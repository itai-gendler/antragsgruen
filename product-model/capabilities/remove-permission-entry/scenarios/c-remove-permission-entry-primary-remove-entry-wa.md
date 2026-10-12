---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove entry"
  },
  "steps": [
    {
      "text": "Remove permission entry request: Remove entry.",
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
      "text": "Selected group entry is removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "permission-entry",
          "effect": "removes"
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

# Remove permission entry — Remove entry — WA

## Trigger

Remove permission entry request: Remove entry.

## Outcome

Selected group entry is removed.
