---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove Membership"
  },
  "steps": [
    {
      "text": "Remove user from group request: Remove Membership.",
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
      "text": "Applicable membership is removed after actual site/self-lockout checks.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "membership",
          "effect": "removes"
        },
        {
          "entity": "site",
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

# Remove user from group — Remove Membership — WA

## Trigger

Remove user from group request: Remove Membership.

## Outcome

Applicable membership is removed after actual site/self-lockout checks.
