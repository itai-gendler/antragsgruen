---
{
  "kind": "validation",
  "routes": {
    "route": "WA Invalid/refused creation"
  },
  "steps": [
    {
      "text": "Create user group request: Invalid/refused creation.",
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
      "text": "Name/group input is invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Create user group — Invalid/refused creation — WA

## Trigger

Create user group request: Invalid/refused creation.

## Outcome

Name/group input is invalid. This attempt does not complete the requested operation.
