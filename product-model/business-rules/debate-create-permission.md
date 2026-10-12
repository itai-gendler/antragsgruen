---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "debate",
      "effect": "creates",
      "contexts": [
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::consultation"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "consultation"
    },
    {
      "configuredBy": "permission-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/DebateItem.php"
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

# Debate create is available to the configured administrators

Moderation requires enabled debate feature and unrestricted DEBATE_MODERATION. Reading preserves common Base access and actual target/attachment disclosure. Derived document invisibility ends the current entry while retaining history; agenda-item deletion deletes associated history under its agenda parent operation.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
