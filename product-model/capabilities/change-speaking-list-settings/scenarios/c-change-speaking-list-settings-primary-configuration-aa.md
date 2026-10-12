---
{
  "kind": "primary",
  "routes": {
    "route": "AA Configuration"
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
          "place": "antragsgruen-api::authenticated"
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
          "place": "antragsgruen-api::authenticated"
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

# Change speaking-list settings — Configuration — AA

## Trigger

Change speaking-list settings request: Configuration.

## Outcome

Settings/open gates persist; activating an unassigned queue deactivates other unassigned queues.
