---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "consultation",
      "effect": "changes",
      "facts": [
        "Deleted"
      ],
      "contexts": [
        {
          "place": "web::authenticated::consultations"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "permission-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Consultation.php"
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

# Consultation delete is available to the configured administrators

SITE_ADMIN removes selected nondefault consultations. The posted key must strictly equal the stored key; default selection cannot be deleted.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
