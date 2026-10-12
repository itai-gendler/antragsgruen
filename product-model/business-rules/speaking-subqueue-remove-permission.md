---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "speaking-subqueue",
      "effect": "removes",
      "contexts": [
        {
          "place": "web::authenticated::consultation-settings"
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
      "target": "models/db/SpeechSubqueue.php"
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

# Speaking subqueue remove is available to the configured administrators

Subqueue configuration uses Appearance under unrestricted CONSULTATION_SETTINGS across lists, not the speech REST settings endpoint. Names/order and removal/reassignment retain actual setSubqueueConfiguration behavior; reading follows queue disclosure.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
