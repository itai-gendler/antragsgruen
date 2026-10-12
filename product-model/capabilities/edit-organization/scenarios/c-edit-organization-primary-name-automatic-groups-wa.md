---
{
  "kind": "primary",
  "routes": {
    "route": "WA Name/automatic groups"
  },
  "steps": [
    {
      "text": "Edit organization request: Name/automatic groups.",
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
      "text": "Selected name/automatic group assignments change.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "organization",
          "effect": "changes",
          "facts": [
            "Name",
            "Automatic groups"
          ]
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

# Edit organization — Name/automatic groups — WA

## Trigger

Edit organization request: Name/automatic groups.

## Outcome

Selected name/automatic group assignments change.
