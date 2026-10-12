---
{
  "kind": "primary",
  "routes": {
    "route": "AA Staff entry"
  },
  "steps": [
    {
      "text": "Add speaker request: Staff entry.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
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
      "text": "A staff application persists with selected account/name and subqueue.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "creates",
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
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
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

# Add speaker — Staff entry — AA

## Trigger

Add speaker request: Staff entry.

## Outcome

A staff application persists with selected account/name and subqueue.
