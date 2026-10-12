---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-proposed-procedure",
      "effect": "changes",
      "facts": [
        "Notification information"
      ],
      "contexts": [
        {
          "place": "web::authenticated::procedure-administration"
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
      "target": "models/db/MotionProposal.php"
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

# Motion proposed procedure change limited is available to the configured administrators

Limited procedure is scoped CHANGE_PROPOSALS or unrestricted CONSULTATION_SETTINGS. Notification/communication changes do not require full publication editability.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
