---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Password configuration"
      ],
      "contexts": [
        {
          "place": "web::public::sign-in"
        },
        {
          "place": "web::authenticated::sign-in"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "challenges",
          "entity": "visitor"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "is challenged by",
          "entity": "user"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/UserGroupPermissionEntry.php#containsPrivilege"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php#hasPrivilege"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/UsersController.php#actionSave"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php"
    }
  ]
}
---

# Pending Account password change targets its retained authentication challenge

Forced password change resolves the target held by the ongoing Visitor or User authentication challenge. It changes that target, which may differ from the current signed-in account. Required local password constraints and challenge proof are checked by the authentication invariant; administration grants no challenge bypass.
