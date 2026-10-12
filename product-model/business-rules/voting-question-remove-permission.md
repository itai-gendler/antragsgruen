---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "voting-question",
      "effect": "removes",
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
      "target": "models/db/VotingQuestion.php"
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

# Voting question remove is available to the configured administrators

Question operations inherit the actual VOTINGS or debate parent operation. Preparation/grouping restrictions and participant/result disclosure follow their actual ballot contexts. Closing/resetting stores or clears computed results separately from document disposition.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
