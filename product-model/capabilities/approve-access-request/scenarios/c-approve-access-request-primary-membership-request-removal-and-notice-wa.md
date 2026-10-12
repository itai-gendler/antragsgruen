---
{
  "kind": "primary",
  "routes": {
    "route": "WA Membership, request removal and notice"
  },
  "steps": [
    {
      "text": "Approve access request request: Membership, request removal and notice.",
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
      "text": "Default participant membership is created, approval mail is sent and pending request removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "access-request",
          "effect": "removes"
        },
        {
          "entity": "membership",
          "effect": "creates",
          "facts": [
            "Account",
            "Group",
            "Container"
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

# Approve access request — Membership, request removal and notice — WA

## Trigger

Approve access request request: Membership, request removal and notice.

## Outcome

Default participant membership is created, approval mail is sent and pending request removed.
