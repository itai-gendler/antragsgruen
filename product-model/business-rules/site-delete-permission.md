---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "site",
      "effect": "changes",
      "facts": [
        "Deleted"
      ],
      "contexts": [
        {
          "place": "web::authenticated::consultation-administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "permission-entry"
    },
    {
      "configuredBy": "installation-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Site.php"
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

# Site delete is available to the configured administrators

Index administrative entry accepts CONSULTATION_SETTINGS or SITE_ADMIN. The delete-site branch adds no inferred stronger SITE_ADMIN-only check.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
