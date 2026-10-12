---
{
  "kind": "validation",
  "routes": {
    "route": "WA Removal refused"
  },
  "steps": [
    {
      "text": "Remove organization request: Removal refused.",
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
      "text": "Organization/removal request is unavailable. This attempt does not complete the requested operation.",
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

# Remove organization — Removal refused — WA

## Trigger

Remove organization request: Removal refused.

## Outcome

Organization/removal request is unavailable. This attempt does not complete the requested operation.
