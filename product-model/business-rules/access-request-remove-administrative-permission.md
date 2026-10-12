---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "access-request",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::user-administration"
        },
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
      "target": "controllers/admin/UsersController.php"
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

# Administrative Access request removal follows its actual operation authority

Request rejection in Users administration requires unrestricted CONSULTATION_SETTINGS and removes the request without creating membership. Cleanup through administrative Account deactivation additionally inherits the parent GLOBAL_USER_ADMIN and self-lockout checks. Applicable group templates and installation administrator assignments participate.
