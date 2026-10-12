---
{
  "kind": "primary",
  "routes": {
    "route": "WA Editable consultation group"
  },
  "steps": [
    {
      "text": "Create user group request: Editable selected item group.",
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
      "text": "A named editable consultation group persists.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user-group",
          "effect": "creates",
          "facts": [
            "Name",
            "Scope",
            "Template",
            "Selectability",
            "Permissions"
          ]
        },
        {
          "entity": "consultation",
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

# Create user group — Editable consultation group — WA

## Trigger

Create user group request: Editable consultation group.

## Outcome

A named editable consultation group persists.
