---
{
  "kind": "validation",
  "routes": {
    "route": "WA Rejection refused"
  },
  "steps": [
    {
      "text": "Reject access request request: Rejection refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "access-request",
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
      "text": "Pending request cannot be processed. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "access-request",
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

# Reject access request — Rejection refused — WA

## Trigger

Reject access request request: Rejection refused.

## Outcome

Pending request cannot be processed. This attempt does not complete the requested operation.
