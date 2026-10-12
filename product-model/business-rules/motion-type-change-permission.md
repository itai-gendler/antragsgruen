---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-type",
      "effect": "changes",
      "contexts": [
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

# Motion type change is available to the configured administrators

Unrestricted CONSULTATION_SETTINGS edits type configuration; the implemented API metadata/settings projection does not imply Web section administration.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
