---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "consultation",
      "effect": "changes",
      "facts": [
        "Participation settings",
        "Display settings"
      ],
      "contexts": [
        {
          "place": "web::authenticated::consultation-settings"
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

# Consultation change settings is available to the configured administrators

Unrestricted CONSULTATION_SETTINGS controls consultation participation/access and behavioral appearance sections.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
