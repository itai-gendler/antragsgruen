---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "access-request",
      "effect": "creates",
      "contexts": [
        {
          "place": "web::authenticated::consultation-access"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "identifies",
          "entity": "user"
        }
      ]
    },
    {
      "configuredBy": "permission-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/UsersController.php"
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

# Access request create is available to the owner and configured administrators

Identified account requesting is gated by allowRequestingAccess and actual access/request state. Consultation administration processes requests under unrestricted CONSULTATION_SETTINGS; approval supplies default participant membership and mail, rejection removes without membership. Account lifecycle cleanup retains its parent authority.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
