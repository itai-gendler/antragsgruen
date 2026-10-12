---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment",
      "effect": "changes",
      "facts": [
        "Changes",
        "Reason"
      ],
      "contexts": [
        {
          "place": "web::authenticated::amendment-administration"
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

# Amendment edit admin text is available to the configured administrators

Administrative text saving requires scoped STATUS_EDIT and scoped TEXT_EDIT, after the editor-entry alternatives.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
