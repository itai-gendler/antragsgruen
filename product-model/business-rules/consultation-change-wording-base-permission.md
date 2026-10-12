---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "consultation",
      "effect": "changes",
      "facts": [
        "Wording base"
      ],
      "contexts": [
        {
          "place": "web::authenticated::translation-wording"
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
      "target": "models/db/Consultation.php"
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

# Consultation change wording base is available to the configured administrators

Unrestricted CONSULTATION_SETTINGS selects the consultation wording base.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
