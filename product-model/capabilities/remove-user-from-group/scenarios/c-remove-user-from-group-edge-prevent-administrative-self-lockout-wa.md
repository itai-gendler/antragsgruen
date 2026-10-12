---
{
  "kind": "edge",
  "routes": {
    "route": "WA Prevent administrative self-lockout"
  },
  "steps": [
    {
      "text": "Remove user from group request: Prevent administrative self-lockout.",
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
          "place": "web::authenticated::user-account-administration"
        }
      }
    },
    {
      "text": "Ordinary removal prevents administrative self-lockout; imports follow a different membership-write path.",
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
          "place": "web::authenticated::user-account-administration"
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

# Remove user from group — Prevent administrative self-lockout — WA

## Trigger

Remove user from group request: Prevent administrative self-lockout.

## Outcome

Ordinary removal prevents administrative self-lockout; imports follow a different membership-write path.
