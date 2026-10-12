---
{
  "kind": "primary",
  "routes": {
    "route": "WA Name/automatic groups"
  },
  "steps": [
    {
      "text": "Create organization request: Name/automatic groups.",
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
      "text": "Name and valid automatic consultation-group assignments persist.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "organization",
          "effect": "creates",
          "facts": [
            "Name",
            "Automatic groups"
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

# Create organization — Name/automatic groups — WA

## Trigger

Create organization request: Name/automatic groups.

## Outcome

Name and valid automatic consultation-group assignments persist.
