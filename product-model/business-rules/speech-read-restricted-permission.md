---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "speech",
      "effect": "reads",
      "facts": [
        "Identity",
        "Name"
      ],
      "contexts": [
        {
          "place": "antragsgruen-api::authenticated"
        },
        {
          "place": "web::authenticated::speaking-list"
        },
        {
          "place": "web::public::speaking-list"
        },
        {
          "place": "antragsgruen-api::public"
        },
        {
          "place": "web::authenticated::speaking-list-administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "configuredBy": "speaking-list"
    },
    {
      "configuredBy": "permission-entry"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechQueueItem.php"
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

# Speech read restricted is available to the configured administrators

Application uses actual ordinary/point-of-order open flags, account or guest cookie when login is not required, configured naming/subqueue and duplicate checks. SPEECH_QUEUES permits staff addition/order/slot/timing/removal/reset. Withdrawal uses matching account/cookie ownership only for an unstarted application. Identity/name disclosure follows queue configuration. Appearance subqueue removal reassigns affected entries through its configuration authority.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
