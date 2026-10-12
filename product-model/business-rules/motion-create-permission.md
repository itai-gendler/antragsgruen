---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "creates",
      "contexts": [
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::motion-submission"
        },
        {
          "place": "web::public::motion-submission"
        }
      ]
    }
  ],
  "permits": [
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

# Motion create is available to the configured participants

Creation follows the corresponding Motion-type participation policy and deadline with its implemented administrative override. Amendment creation additionally checks actual base/type amendability, language and child depth; API Motion creation is immediate, Web creation is a Draft.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
