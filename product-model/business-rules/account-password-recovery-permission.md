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
          "place": "web::public::password-recovery"
        },
        {
          "place": "web::authenticated::password-recovery"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor",
        "user"
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

# Account password recovery is available in either Web context

Visitor and User may invoke the local recovery process. Account lookup, captcha, request-rate checks and recovery-token proof are authentication/request validation, not an ownership or administration grant. Account change restrictions are checked at the implemented request stage. The actual matching recovery proof identifies the target for completion.
