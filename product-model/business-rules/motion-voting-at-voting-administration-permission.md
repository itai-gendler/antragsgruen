---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "changes",
      "facts": [
        "Voting information"
      ],
      "contexts": [
        {
          "place": "web::authenticated::voting-administration"
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

# Motion voting at voting administration is available to the configured administrators

Voting administration assigns/removes document items with unrestricted VOTINGS, preserving supported grouping phases.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
