---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment-proposed-procedure",
      "effect": "changes",
      "facts": [
        "Recommendation",
        "Explanation",
        "Version",
        "Alternative text"
      ],
      "contexts": [
        {
          "place": "web::authenticated::procedure-administration"
        },
        {
          "place": "web::authenticated::proposed-change-editor"
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
      "target": "models/db/AmendmentProposal.php"
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

# Amendment proposed procedure change full is available to the configured administrators

Full procedure requires Limited procedure, plus ppEditableAfterPublication when public or unrestricted CONSULTATION_SETTINGS override.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
