---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "speaking-list",
      "effect": "changes",
      "contexts": [
        {
          "place": "web::authenticated::speaking-list-administration"
        },
        {
          "place": "antragsgruen-api::authenticated"
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
      "target": "models/db/SpeechQueue.php"
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

# Speaking list change is available to the configured administrators

Public/application reading follows actual queue/consultation disclosure. Queue administration requires unrestricted SPEECH_QUEUES; associated creation/removal follows actual agenda/configuration/debate parent authority. Debate moderation can create/activate its queue with unrestricted DEBATE_MODERATION. Activation exclusivity applies only among unassigned lists.

Group entries are alternatives. Scope resolution tests the entry’s tag restriction first, otherwise agenda restriction, otherwise Motion-type restriction. A restricted entry does not pass an unrestricted (null-context) check. Applicable shipped group templates and installation administrator assignments participate as implemented.
