---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "motion",
      "effect": "reads",
      "contexts": [
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::motion"
        },
        {
          "place": "web::public::motion"
        },
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "web::authenticated::consultation"
        },
        {
          "place": "web::public::consultation"
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

# Motion read document is available to the configured administrators

Direct readability follows unreadable statuses; it does not require public-list visibility. Draft/administrative-draft direct reads require unrestricted CONTENT_EDIT. Section/protocol/voting disclosure retain their own publicity. Public lists apply their separate visibility filtering.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
