---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "voting-activity",
      "effect": "reads",
      "contexts": [
        {
          "place": "antragsgruen-api::authenticated"
        },
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
      "target": "models/api/voting/VotingActivityLogEntry.php"
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

# Voting activity read is available to the configured administrators

Visible voting activity disclosure is part of unrestricted VOTINGS administration.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
