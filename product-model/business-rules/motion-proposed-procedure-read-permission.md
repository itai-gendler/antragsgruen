---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion-proposed-procedure",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::public::proposed-procedure"
        },
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::proposed-procedure"
        },
        {
          "place": "web::authenticated::procedure-administration"
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

# Motion proposed procedure read is available to the configured administrators

Published procedure is readable through its actual document/consultation gate. Requested-feedback alternative visibility and scoped CHANGE_PROPOSALS staff disclosure are distinct implemented branches.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
