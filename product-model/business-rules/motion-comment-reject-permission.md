---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-comment",
      "effect": "changes",
      "facts": [
        "Screening"
      ],
      "contexts": [
        {
          "place": "web::authenticated::motion"
        }
      ],
      "to": "Deleted"
    }
  ],
  "permits": [
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
      "target": "controllers/MotionActionsTrait.php#screenCommentReject"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionActionsTrait.php#performShowActions"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionActionsTrait.php#getComment"
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

# Motion comment rejection requires unrestricted screening authority

This Rule evaluates the additional screening requirement for the operation actually dispatched by performShowActions.

When deleteComment is dispatched, this Rule imposes no additional SCREENING requirement. It passes without requiring group membership or an installation-administrator assignment. The separate Visible-to-Deleted Rule still requires ownership or contextual screening authority.

When screenCommentReject is dispatched, the alternatives are:

- One of the current User's actual groups applicable to this consultation grants SCREENING with a null PrivilegeQueryContext.
- The current User's id appears in the actual installation settings' adminUserIds.

Ownership alone never passes the rejection requirement. A tag-, agenda- or Motion-type-restricted permission entry does not pass the null-context check. Applicable stored default/template permissions are evaluated as implemented.

The operation follows controller dispatch, not the requested resulting state. deleteComment takes precedence over commentScreeningAccept and commentScreeningReject when multiple dispatch fields are present.

Document identity and record lookup remain independent request validation. Delete requires a matching Visible comment. Reject requires a matching comment but adds no Pending-only or Visible-only status precondition; the inherited lookup excludes already Deleted comments. These checks are not authorization configuration.
