---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "changes",
      "facts": [
        "Procedure tags"
      ],
      "contexts": [
        {
          "place": "web::authenticated::procedure-administration"
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
      "target": "models/db/Motion.php"
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

# Motion procedure tags at administration is available to the configured administrators

The dedicated procedure-tag controller uses any-restriction CHANGE_PROPOSALS entry and adds no per-document/full-publication-lock check.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
