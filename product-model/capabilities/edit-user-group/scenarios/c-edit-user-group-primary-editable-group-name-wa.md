---
{
  "kind": "primary",
  "routes": {
    "route": "WA Editable group name"
  },
  "steps": [
    {
      "text": "Edit user group request: Editable group name.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "user-group",
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
      "text": "Editable group name changes.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user-group",
          "effect": "changes",
          "facts": [
            "Name"
          ]
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

# Edit user group — Editable group name — WA

## Trigger

Edit user group request: Editable group name.

## Outcome

Editable group name changes.
