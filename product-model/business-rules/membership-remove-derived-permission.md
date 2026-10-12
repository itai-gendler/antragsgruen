---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "membership",
      "effect": "removes",
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
          "verb": "owns",
          "entity": "account"
        },
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

# Personal Membership cleanup follows Account deactivation

The own account’s group links are removed as effects of confirmed personal Account deactivation under its usable-account-page and allowAccountDeletion checks. No consultation-administration privilege is required of the owner for this cleanup.
