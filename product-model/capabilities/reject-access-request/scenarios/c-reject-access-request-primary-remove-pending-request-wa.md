---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove pending request"
  },
  "steps": [
    {
      "text": "Reject access request request: Remove pending request.",
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
      "text": "Pending request is removed without creating membership.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "access-request",
          "effect": "removes"
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

# Reject access request — Remove pending request — WA

## Trigger

Reject access request request: Remove pending request.

## Outcome

Pending request is removed without creating membership.
