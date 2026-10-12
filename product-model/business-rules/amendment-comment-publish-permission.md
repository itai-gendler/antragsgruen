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
      "to": "Visible"
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
      "target": "controllers/AmendmentActionsTrait.php#screenCommentAccept"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/AmendmentComment.php"
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
    }
  ]
}
---

# Amendment comment publish is available to the configured administrators

Motion comment publication requires unrestricted SCREENING; Amendment comment publication requires its contextual SCREENING check.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented. The source screening handler accepts a matching comment without a current-status precondition.
