---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "wording-override",
      "effect": "creates",
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
      "target": "models/db/ConsultationText.php"
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

# Wording override create is available to the configured administrators

Unrestricted CONSULTATION_SETTINGS governs individual addressed wording entries; nonempty input adds/edits and empty replacement removes the selected entry.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
