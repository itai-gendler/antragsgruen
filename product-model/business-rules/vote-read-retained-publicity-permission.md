---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "vote",
      "effect": "reads",
      "facts": [
        "Retained publicity",
        "Account"
      ],
      "contexts": [
        {
          "place": "web::authenticated::voting-results"
        },
        {
          "place": "antragsgruen-api::authenticated"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "identifies",
          "entity": "user"
        }
      ]
    },
    {
      "configuredBy": "voting"
    },
    {
      "configuredBy": "permission-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Vote.php"
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

# Vote read retained publicity is available to the owner and configured administrators

Voting participation checks configured policy with administrative override disabled, Open phase, applicable maximum, duplicate refusal and mutual exclusion with general abstention. Server chooses stored weight. Own/current/retained publicity gates payload reading; secret payloads disclose no voter identities even to administrators. Undo needs the owned Open vote but no fresh eligibility check; VOTINGS reset/removal clears votes. Download export uses its current votesPublic branch and does not promise full payload retained-publicity protection. Answer/input proof remains validation.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
