---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::authenticated::motion-administration-list"
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
      "target": "models/db/Amendment.php"
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

# Amendment read list is available to the configured administrators

Administrative list entry accepts any-restriction SEE_UNPUBLISHED, SCREENING, CHANGE_PROPOSALS, MOTION_DELETE or MOTION_STATUS_EDIT. Source list filters/disclosure do not establish a universal per-row privilege check.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
