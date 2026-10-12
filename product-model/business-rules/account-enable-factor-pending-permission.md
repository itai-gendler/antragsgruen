---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Second-factor configuration"
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

# Pending Account factor enrollment targets its retained authentication challenge

Required enrollment resolves the account held by the Visitor or User’s actual ongoing enrollment session, which can differ from the current signed-in account. Enrollment-session lifetime and factor proof are authentication validation; owner or administration authority does not bypass that pending-target resolution.
