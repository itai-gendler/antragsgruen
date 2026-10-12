---
{
  "kind": "validation",
  "routes": {
    "route": "WA Addition refused"
  },
  "steps": [
    {
      "text": "Add user to group request: Addition refused.",
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
      "text": "Group/account scope or selectability fails. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "membership",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "account",
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

# Add user to group — Addition refused — WA

## Trigger

Add user to group request: Addition refused.

## Outcome

Group/account scope or selectability fails. This attempt does not complete the requested operation.
