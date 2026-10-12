---
{
  "kind": "primary",
  "routes": {
    "route": "WA Configuration"
  },
  "steps": [
    {
      "text": "Change speaking-list settings request: Configuration.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::speaking-list-administration"
        }
      }
    },
    {
      "text": "Settings/open gates persist; activating an unassigned queue deactivates other unassigned queues.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "changes",
          "facts": [
            "Active",
            "Open flags",
            "Naming",
            "Timing"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::speaking-list-administration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/SpeechController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/SpeechQueue.php"
    }
  ]
}
---

# Change speaking-list settings — Configuration — WA

## Trigger

Change speaking-list settings request: Configuration.

## Outcome

Settings/open gates persist; activating an unassigned queue deactivates other unassigned queues.
