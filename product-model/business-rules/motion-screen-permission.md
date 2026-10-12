---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "changes",
      "facts": [
        "Disposition",
        "Submission information"
      ],
      "contexts": [
        {
          "place": "web::authenticated::motion-administration"
        },
        {
          "place": "antragsgruen-api::authenticated"
        }
      ],
      "to": "Screened"
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

# Motion screen is available to the configured administrators

The dedicated screen operation requires the contextual SCREENING privilege and a source in its screening process. Administrative status Save can independently assign a screened disposition through STATUS_EDIT.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
