---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "amendment",
      "effect": "changes",
      "facts": [
        "Disposition"
      ],
      "contexts": [
        {
          "place": "web::authenticated::amendment-administration"
        }
      ],
      "to": "Deleted"
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
      "target": "models/db/Amendment.php"
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

# Amendment delete is available to the configured administrators

The delete button requires editor entry (one of scoped STATUS_EDIT/TEXT_EDIT/INITIATORS) plus scoped MOTION_DELETE. Posted Deleted disposition through full Save instead requires scoped STATUS_EDIT; all of that Save’s affected detail facts also remain selected by the detail rule.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
