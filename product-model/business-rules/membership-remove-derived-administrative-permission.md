---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "membership",
      "effect": "removes",
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
      "target": "components/UserGroupAdminMethods.php"
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
    }
  ]
}
---

# Administrative Membership cleanup follows Account deactivation

Administrative Account deactivation removes the selected account’s memberships under the parent unrestricted CONSULTATION_SETTINGS and GLOBAL_USER_ADMIN checks and the administrative self-lockout refusal. The parent authority, not a personal ownership bypass, governs this derived cleanup.
