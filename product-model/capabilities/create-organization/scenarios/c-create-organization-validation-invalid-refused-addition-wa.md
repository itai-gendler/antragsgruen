---
{
  "kind": "validation",
  "routes": {
    "route": "WA Invalid/refused addition"
  },
  "steps": [
    {
      "text": "Create organization request: Invalid/refused addition.",
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
      "text": "Name/groups input is invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Create organization — Invalid/refused addition — WA

## Trigger

Create organization request: Invalid/refused addition.

## Outcome

Name/groups input is invalid. This attempt does not complete the requested operation.
