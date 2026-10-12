---
{
  "kind": "edge",
  "routes": {
    "route": "WA Stops another ongoing speech"
  },
  "steps": [
    {
      "text": "Start speech request: Stops another ongoing speech.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "reads",
          "facts": [],
          "as": "previous"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::speaking-list-administration"
        }
      }
    },
    {
      "text": "Starting the selected entry records a stop on another ongoing speech.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speech",
          "effect": "changes",
          "facts": [
            "Start time"
          ],
          "as": "selected"
        },
        {
          "entity": "speech",
          "effect": "changes",
          "facts": [
            "Stop time"
          ],
          "as": "previous"
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

# Start speech — Stops another ongoing speech — WA

## Trigger

Start speech request: Stops another ongoing speech.

## Outcome

Starting the selected entry records a stop on another ongoing speech.
