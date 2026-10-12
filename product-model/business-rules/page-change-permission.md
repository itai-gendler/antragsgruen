---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "page",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::page"
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
    },
    {
      "configuredBy": "installation-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
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

# Page change is available to the configured administrators

Scoped content writes require unrestricted CONTENT_EDIT; installation-global pages use configured installation administrator accounts. Web site-wide page reading skips consultation-scoped read policy; REST page reading applies it and Base access using session identity. Applicable privacy/legal/maintenance reading exceptions remain path-specific.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
