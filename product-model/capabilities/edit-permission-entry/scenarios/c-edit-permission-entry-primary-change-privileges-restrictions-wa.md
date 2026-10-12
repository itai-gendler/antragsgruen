---
{
  "kind": "primary",
  "routes": {
    "route": "WA Change privileges/restrictions"
  },
  "steps": [
    {
      "text": "Edit permission entry request: Change privileges/restrictions.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "permission-entry",
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
      "text": "Privileges/restrictions change; scope matching keeps tag then agenda then type priority.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "permission-entry",
          "effect": "changes",
          "facts": [
            "Privileges",
            "Tag restriction",
            "Agenda restriction",
            "Type restriction"
          ]
        },
        {
          "entity": "tag",
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

# Edit permission entry — Change privileges/restrictions — WA

## Trigger

Edit permission entry request: Change privileges/restrictions.

## Outcome

Privileges/restrictions change; scope resolution keeps tag then agenda then type priority.
