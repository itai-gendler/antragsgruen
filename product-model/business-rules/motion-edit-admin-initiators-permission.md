---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "changes",
      "facts": [
        "Initiators"
      ],
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

# Motion edit admin initiators is available to the configured administrators

Administrative initiator saving retains editor entry, scoped STATUS_EDIT and scoped MOTION_INITIATORS.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
