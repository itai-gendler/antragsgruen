---
{
  "kind": "primary",
  "routes": {
    "route": "WA Randomize waiting entries"
  },
  "steps": [
    {
      "text": "Randomize speaking list request: Randomize waiting entries.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "reads",
          "facts": []
        },
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
      "text": "Waiting entries receive randomized application order.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "changes",
          "facts": [
            "Application order"
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

# Randomize speaking list — Randomize waiting entries — WA

## Trigger

Randomize speaking list request: Randomize waiting entries.

## Outcome

Waiting entries receive randomized application order.
