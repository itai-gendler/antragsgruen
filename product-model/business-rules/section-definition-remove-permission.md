---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "section-definition",
      "effect": "changes",
      "facts": [
        "Removed"
      ],
      "contexts": [
        {
          "place": "web::authenticated::motion-type"
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
      "target": "models/db/ConsultationSettingsMotionSection.php"
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

# Section definition remove is available to the configured administrators

Unrestricted CONSULTATION_SETTINGS governs addressed type-section configuration.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
