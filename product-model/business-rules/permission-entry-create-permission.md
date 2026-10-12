---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "permission-entry",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::user-group-administration"
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
      "target": "models/settings/UserGroupPermissionEntry.php"
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

# Permission entry create is available to the configured administrators

Unrestricted CONSULTATION_SETTINGS and actual group editability control addressed entries. Unknown privileges/scopes and restrictions on nonmotion privileges are invalid input; scope priority is tag, agenda, then type.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
