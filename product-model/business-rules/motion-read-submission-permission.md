---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::public::motion-submission"
        },
        {
          "place": "web::authenticated::motion-submission"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "has",
          "entity": "supporter"
        },
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "identifies",
          "entity": "user"
        }
      ],
      "when": [
        {
          "entity": "supporter",
          "fact": "Role",
          "is": "Initiator"
        }
      ]
    },
    {
      "configuredBy": "motion-type"
    },
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

# Motion read submission is available to the configured participants

Draft submission/editor reading admits a signed-in initiator, or anyone when no signed initiator exists and the corresponding policy is All, or unrestricted MOTION_TEXT_EDIT. Confirmation also rechecks the corresponding ordinary creation policy/deadline.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
