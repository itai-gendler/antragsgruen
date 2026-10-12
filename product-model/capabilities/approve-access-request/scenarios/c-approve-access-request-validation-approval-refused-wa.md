---
{
  "kind": "validation",
  "routes": {
    "route": "WA Approval refused"
  },
  "steps": [
    {
      "text": "Approve access request request: Approval refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "access-request",
          "effect": "reads",
          "facts": []
        },
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
      "text": "Pending request cannot be processed. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "access-request",
          "effect": "reads",
          "facts": []
        },
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

# Approve access request — Approval refused — WA

## Trigger

Approve access request request: Approval refused.

## Outcome

Pending request cannot be processed. This attempt does not complete the requested operation.
