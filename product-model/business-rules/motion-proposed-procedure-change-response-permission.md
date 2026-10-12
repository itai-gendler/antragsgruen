---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-proposed-procedure",
      "effect": "changes",
      "facts": [
        "Proposer response"
      ],
      "contexts": [
        {
          "place": "web::public::motion"
        },
        {
          "place": "web::authenticated::motion"
        },
        {
          "place": "web::authenticated::procedure-administration"
        },
        {
          "place": "web::authenticated::proposed-change-editor"
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

# Motion proposed procedure change response is available to the configured administrators

Initiator feedback requires requested feedback and matching procedure token or the actual identified initiator; accepted response is terminal on that path. Staff recording/reset uses Limited procedure. Full recommendation/alternative changes reset response as part of their actual parent operation.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
