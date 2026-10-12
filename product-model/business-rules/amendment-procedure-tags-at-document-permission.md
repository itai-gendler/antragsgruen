---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment",
      "effect": "changes",
      "facts": [
        "Procedure tags"
      ],
      "contexts": [
        {
          "place": "web::authenticated::amendment"
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
      "target": "models/db/Amendment.php"
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

# Amendment procedure tags at document is available to the configured administrators

The document widget’s procedure-tag operation requires Limited procedure: scoped CHANGE_PROPOSALS or unrestricted CONSULTATION_SETTINGS.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
