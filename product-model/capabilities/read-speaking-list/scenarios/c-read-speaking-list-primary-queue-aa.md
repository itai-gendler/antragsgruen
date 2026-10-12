---
{
  "kind": "primary",
  "routes": {
    "route": "AA Queue"
  },
  "steps": [
    {
      "text": "Read selected queue request: Queue.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "Queue, configured names, waiting order and timing are returned.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "reads",
          "facts": [
            "Target",
            "Active",
            "Open flags",
            "Naming",
            "Timing"
          ]
        },
        {
          "entity": "speech",
          "effect": "reads",
          "facts": [
            "Identity",
            "Name",
            "Subqueue",
            "Point of order",
            "Application order",
            "Slot",
            "Start time",
            "Stop time"
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

# Read speaking list — Queue — AA

## Trigger

Read speaking list request: Queue.

## Outcome

Queue, configured names, waiting order and timing are returned.
