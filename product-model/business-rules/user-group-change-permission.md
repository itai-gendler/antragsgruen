---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-group",
      "effect": "changes",
      "facts": [
        "Name"
      ],
      "contexts": [
        {
          "place": "web::authenticated::user-group-administration"
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
      "target": "models/db/ConsultationUserGroup.php"
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

# User group change is available to the configured administrators

Unrestricted CONSULTATION_SETTINGS controls consultation groups; actual site scope, template/editability and membership selection checks remain. Deletion retains default-group fallback.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
