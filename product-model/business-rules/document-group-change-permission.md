---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "document-group",
      "effect": "changes",
      "facts": [
        "Order"
      ],
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
      "target": "models/db/ConsultationFileGroup.php"
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

# Document group change is available to the configured administrators

Group/file mutations require unrestricted CONTENT_EDIT and actual consultation/page parent scope. Reading follows the containing consultation/page access and read policy; removing a group removes its contained uploads.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
