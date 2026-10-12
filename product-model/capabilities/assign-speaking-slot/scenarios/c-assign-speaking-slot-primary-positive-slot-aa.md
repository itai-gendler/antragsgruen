---
{
  "kind": "primary",
  "routes": {
    "route": "AA Positive slot"
  },
  "steps": [
    {
      "text": "Assign speaking slot request: Positive slot.",
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
      "text": "A positive slot is assigned and applicable timing resets.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "changes",
          "facts": [
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

# Assign speaking slot — Positive slot — AA

## Trigger

Assign speaking slot request: Positive slot.

## Outcome

A positive slot is assigned and applicable timing resets.
