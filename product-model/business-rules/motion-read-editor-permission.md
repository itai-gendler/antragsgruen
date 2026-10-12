---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::motion-administration"
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

# Motion read editor is available to the configured administrators

Administrative editor entry accepts any scoped MOTION_STATUS_EDIT, MOTION_TEXT_EDIT or MOTION_INITIATORS. Saving details needs scoped STATUS_EDIT; text and initiator changes retain their additional checks.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
