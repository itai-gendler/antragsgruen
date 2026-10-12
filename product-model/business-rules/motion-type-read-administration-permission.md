---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-type",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::consultation-administration"
        },
        {
          "place": "web::authenticated::motion-type"
        },
        {
          "place": "antragsgruen-api::authenticated"
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
      "target": "models/db/ConsultationMotionType.php"
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

# Motion type read administration is available to the configured administrators

Type configuration disclosure requires unrestricted CONSULTATION_SETTINGS.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
