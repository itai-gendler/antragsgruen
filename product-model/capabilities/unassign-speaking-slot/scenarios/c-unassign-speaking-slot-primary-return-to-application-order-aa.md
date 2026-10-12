---
{
  "kind": "primary",
  "routes": {
    "route": "AA Return to application order"
  },
  "steps": [
    {
      "text": "Unassign speaking slot request: Return to application order.",
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
      "text": "The entry returns to application order and timing resets.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "changes",
          "facts": [
            "Slot",
            "Application order",
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

# Unassign speaking slot — Return to application order — AA

## Trigger

Unassign speaking slot request: Return to application order.

## Outcome

The entry returns to application order and timing resets.
