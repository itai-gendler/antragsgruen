---
{
  "kind": "validation",
  "routes": {
    "route": "WA Start refused"
  },
  "steps": [
    {
      "text": "Start speech request: Start refused.",
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
          "place": "web::authenticated::speaking-list-administration"
        }
      }
    },
    {
      "text": "The selected entry cannot start. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Start speech — Start refused — WA

## Trigger

Start speech request: Start refused.

## Outcome

The selected entry cannot start. This attempt does not complete the requested operation.
