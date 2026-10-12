---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove applicable memberships"
  },
  "steps": [
    {
      "text": "Remove selected item user request: Remove applicable memberships.",
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
      "text": "Applicable consultation memberships are removed without erasing historical record data.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "membership",
          "effect": "removes"
        },
        {
          "entity": "consultation",
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

# Remove consultation user — Remove applicable memberships — WA

## Trigger

Remove consultation user request: Remove applicable memberships.

## Outcome

Applicable consultation memberships are removed without erasing historical document data.
