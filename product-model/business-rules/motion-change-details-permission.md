---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "changes",
      "facts": [
        "Title",
        "Address",
        "Submission information",
        "Flags",
        "Internal note",
        "Relationships",
        "Protocol"
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

# Motion change details is available to the configured administrators

Administrative Save requires scoped STATUS_EDIT and writes details together with the posted disposition, including Deleted if posted. It does not independently invoke the delete-button check. The full Save’s affected non-disposition facts select this rule alongside the disposition outcome rule.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
