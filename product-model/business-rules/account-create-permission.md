---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::sign-in"
        },
        {
          "place": "web::public::sign-in"
        },
        {
          "place": "web::authenticated::user-administration"
        },
        {
          "place": "web::authenticated::user-import"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "installation-settings"
    },
    {
      "configuredBy": "permission-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/User.php"
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

# Account create is available to the configured administrators

Local registration follows allowRegistration, enabled standard login and actual provider creation support. Administrative creation/import requires unrestricted CONSULTATION_SETTINGS. Registration starts Unconfirmed or Confirmed as configured.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
