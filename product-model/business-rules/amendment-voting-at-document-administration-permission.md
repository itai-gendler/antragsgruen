---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment",
      "effect": "changes",
      "facts": [
        "Voting information"
      ],
      "contexts": [
        {
          "place": "web::authenticated::amendment-administration"
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

# Amendment voting at document administration is available to the configured administrators

Administrative assignment/grouping and voting-status fields require scoped MOTION_STATUS_EDIT; new inline ballots start Preparing.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
