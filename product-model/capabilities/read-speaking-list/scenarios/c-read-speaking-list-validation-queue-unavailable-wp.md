---
{
  "kind": "validation",
  "routes": {
    "route": "WP Queue unavailable"
  },
  "steps": [
    {
      "text": "Read speaking list request: Queue unavailable.",
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
          "place": "web::public::speaking-list"
        }
      }
    },
    {
      "text": "The selected queue is unavailable. This attempt does not complete the requested operation.",
      "kind": "condition",
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
          "place": "web::public::speaking-list"
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

# Read speaking list — Queue unavailable — WP

## Trigger

Read speaking list request: Queue unavailable.

## Outcome

The selected queue is unavailable. This attempt does not complete the requested operation.
