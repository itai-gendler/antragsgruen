---
{
  "kind": "validation",
  "routes": {
    "route": "WA Removal refused"
  },
  "steps": [
    {
      "text": "Remove selected item user request: Removal refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "membership",
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
      "text": "Membership removal checks fail. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "membership",
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

# Remove consultation user — Removal refused — WA

## Trigger

Remove consultation user request: Removal refused.

## Outcome

Membership removal checks fail. This attempt does not complete the requested operation.
