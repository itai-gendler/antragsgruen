---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment-comment",
      "effect": "changes",
      "facts": [
        "Screening"
      ],
      "contexts": [
        {
          "place": "web::authenticated::amendment"
        }
      ],
      "to": "Deleted",
      "from": "Visible"
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
    },
    {
      "configuredBy": "user-group"
    },
    {
      "configuredBy": "installation-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentActionsTrait.php#deleteComment"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentActionsTrait.php#performShowActions"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentActionsTrait.php#getComment"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/IComment.php#canDelete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/IComment.php#findByCondition"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php#hasPrivilege"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/UserGroupPermissionEntry.php#containsPrivilege"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/UserGroupPermissions.php#containsPrivilege"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/UserGroupAdminMethods.php#saveUserGroup"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/AntragsgruenApp.php"
    }
  ]
}
---

# Only the owner or a User with contextual screening authority removes a Visible Amendment comment

For a selected Visible-to-Deleted change, the alternatives are:

- The current User is identified by the Account that owns this comment: the comment's retained userId equals the current User's id.
- One of the current User's actual groups applicable to this consultation grants SCREENING for PrivilegeQueryContext::imotion of the comment's Amendment.
- The current User's id appears in the actual installation settings' adminUserIds.

The group alternative evaluates stored group permissions, including implemented default/template permissions. Explicit entries are alternatives. Within an entry, restriction evaluation checks tag first, otherwise agenda item, otherwise Motion type. A present restriction must match the document context before its privilege can grant access.

Ownership is the implemented author relationship, not configurable screening authority. Passing this Rule does not bypass the separate operation-dependent screening requirement.
