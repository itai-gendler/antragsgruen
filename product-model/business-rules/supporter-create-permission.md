---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "supporter",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::public::amendment"
        },
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "web::public::motion"
        },
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::amendment"
        },
        {
          "place": "web::authenticated::motion"
        },
        {
          "place": "web::authenticated::motion-submission"
        },
        {
          "place": "web::public::motion-submission"
        },
        {
          "place": "web::authenticated::amendment-submission"
        },
        {
          "place": "web::public::amendment-submission"
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
      "target": "models/db/ISupporter.php"
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

# Supporter create is available to the configured participants

Initiator creation follows document creation policy. Official support refuses own initiators, requires actual support policy/deadline/state and validates its supplied identity. Reactions require configured Like/Dislike and the support policy with administrative override disabled. Role/target select the actual branch; duplicate official support is unchanged.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
