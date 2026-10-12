---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove entry"
  },
  "steps": [
    {
      "text": "Remove organization request: Remove entry.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "organization",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-administration"
        }
      }
    },
    {
      "text": "Selected organization entry is removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "organization",
          "effect": "removes"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-administration"
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

# Remove organization — Remove entry — WA

## Trigger

Remove organization request: Remove entry.

## Outcome

Selected organization entry is removed.
