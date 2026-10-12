---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment-text-section",
      "effect": "reads",
      "contexts": [
        {
          "place": "web::public::amendment-submission"
        },
        {
          "place": "web::authenticated::amendment-submission"
        },
        {
          "place": "web::authenticated::amendment-administration"
        },
        {
          "place": "web::authenticated::incorporate-amendment"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "permission-entry"
    },
    {
      "configuredBy": "motion-type"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/AmendmentSection.php"
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

# Amendment text section read editor is available to the configured participants

Editing reads follow the selected public-text, administrative-text or source merge authority, without equating those routes.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
