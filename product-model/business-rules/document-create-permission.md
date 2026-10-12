---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "document",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::documents"
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
      "target": "models/db/ConsultationFile.php"
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

# Document create is available to the configured administrators

Uploads/removal require unrestricted CONTENT_EDIT for the actual parent page/group; reading follows the containing page/consultation scope. Generated document exports are projections of their source, not uploaded Documents.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
