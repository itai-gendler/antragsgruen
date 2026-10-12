---
{
  "kind": "edge",
  "routes": {
    "route": "WA Default-group fallback"
  },
  "steps": [
    {
      "text": "Delete user group request: Default-group fallback.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "user-group",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-group-administration"
        }
      }
    },
    {
      "text": "Removed editable groups give applicable accounts the default-group fallback.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "user-group",
          "effect": "removes"
        },
        {
          "entity": "membership",
          "effect": "removes",
          "as": "old",
          "with": "user-group"
        },
        {
          "entity": "membership",
          "effect": "creates",
          "facts": [
            "Account",
            "Group",
            "Container"
          ],
          "as": "fallback"
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-group-administration"
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

# Delete user group — Default-group fallback — WA

## Trigger

Delete user group request: Default-group fallback.

## Outcome

Removed editable groups give applicable accounts the default-group fallback.
