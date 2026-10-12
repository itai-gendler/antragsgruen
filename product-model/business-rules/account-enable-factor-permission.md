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
          "place": "web::authenticated::my-account"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "identifies",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/SecondFactorAuthentication.php"
    }
  ]
}
---

# Personal Account factor controls belong to its identified owner

The acting account owner uses the usable My account form for its own factor configuration. Both enrollment and removal require supportsSecondFactorAuth: email authentication and preventPasswordChange false. Enrollment verifies its prepared key and code; removal verifies a currently enrolled key. The separate pending-enrollment and administrative operations retain their own disjoint grants.
