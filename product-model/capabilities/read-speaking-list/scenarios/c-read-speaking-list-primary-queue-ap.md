---
{
  "kind": "primary",
  "routes": {
    "route": "AP Queue"
  },
  "steps": [
    {
      "text": "Read speaking list request: Queue.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "speaking-list",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "speech",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "antragsgruen-api::public"
        }
      }
    },
    {
      "text": "Queue, configured names, waiting order and timing are returned.",
      "kind": "product",
      "actor": "visitor",
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
          "place": "antragsgruen-api::public"
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

# Read speaking list — Queue — AP

## Trigger

Read speaking list request: Queue.

## Outcome

Queue, configured names, waiting order and timing are returned.
