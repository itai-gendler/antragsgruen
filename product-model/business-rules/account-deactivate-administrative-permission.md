---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Name",
        "Email",
        "Authentication identity",
        "Account restrictions"
      ],
      "contexts": [
        {
          "place": "web::authenticated::user-account-administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "permission-entry"
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
      "target": "controllers/admin/UsersController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php#deleteUser"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/UserController.php#actionMyaccount"
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

# Administrative Account deactivation requires global account authority

The delete-user operation requires unrestricted CONSULTATION_SETTINGS and unrestricted GLOBAL_USER_ADMIN. Its actual installation administrator assignments and group templates participate. Deleting the acting administrator is refused by deleteUser’s self-lockout check; ownership grants no bypass.
