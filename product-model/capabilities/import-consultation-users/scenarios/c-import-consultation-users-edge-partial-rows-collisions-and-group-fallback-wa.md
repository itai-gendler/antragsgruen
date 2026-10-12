---
{
  "kind": "edge",
  "routes": {
    "route": "WA Partial rows, collisions and group fallback"
  },
  "steps": [
    {
      "text": "Import selected item users request: Partial rows, collisions and group fallback.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [],
          "as": "existing"
        },
        {
          "entity": "membership",
          "effect": "reads",
          "facts": [],
          "as": "replaced"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-import"
        }
      }
    },
    {
      "text": "Rows can partially persist; collisions use skip/merge/replace. Missing groups warn and use default fallback; profile/direct membership writes follow the import-specific weaker guards.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Name",
            "Organization"
          ],
          "as": "existing"
        },
        {
          "entity": "membership",
          "effect": "creates",
          "facts": [
            "Account",
            "Group",
            "Container"
          ],
          "as": "added"
        },
        {
          "entity": "membership",
          "effect": "removes",
          "as": "replaced"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::user-import"
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

# Import consultation users — Partial rows, collisions and group fallback — WA

## Trigger

Import consultation users request: Partial rows, collisions and group fallback.

## Outcome

Rows can partially persist; collisions use skip/merge/replace. Missing groups warn and use default fallback; profile/direct membership writes follow the import-specific weaker guards.
