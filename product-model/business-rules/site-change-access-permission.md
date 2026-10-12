---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "site",
      "effect": "changes",
      "facts": [
        "Access settings"
      ],
      "contexts": [
        {
          "place": "web::authenticated::consultation-settings"
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

# Site change access is available to the configured administrators

SITE_ADMIN or the applicable installation administrator assignment controls site access/login configuration. Consultation-settings authority alone does not change guarded site-access fields.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
