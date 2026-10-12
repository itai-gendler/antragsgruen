---
{
  "kind": "primary",
  "routes": {
    "route": "WA Add scoped privilege entry"
  },
  "steps": [
    {
      "text": "Add permission entry request: Add scoped privilege entry.",
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
      "text": "Validated privilege entry and optional restrictions persist.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "permission-entry",
          "effect": "creates",
          "facts": [
            "Privileges",
            "Tag restriction",
            "Agenda restriction",
            "Type restriction"
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

# Add permission entry — Add scoped privilege entry — WA

## Trigger

Add permission entry request: Add scoped privilege entry.

## Outcome

Validated privilege entry and optional restrictions persist.
