---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "voting",
      "effect": "creates",
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
      "target": "models/db/VotingBlock.php"
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

# Voting create procedure is available to the configured administrators

Administrative creation/settings/phase/order/removal use unrestricted VOTINGS. Inline document creation instead uses scoped MOTION_STATUS_EDIT (Preparing); procedure creation uses Limited procedure (Offline); debate creation uses enabled feature and unrestricted DEBATE_MODERATION. Participant/result reads require actual authenticated context and their payload visibility. Ballot fields/grouping remain constrained to supported phases; public results and retained/current vote disclosure are separate.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
