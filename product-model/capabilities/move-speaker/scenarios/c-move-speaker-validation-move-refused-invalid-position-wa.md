---
{
  "kind": "validation",
  "routes": {
    "route": "WA Move refused/invalid position"
  },
  "steps": [
    {
      "text": "Move speaker request: Move refused/invalid position.",
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
      "text": "Entry/target position is invalid. This attempt does not complete the requested operation.",
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

# Move speaker — Move refused/invalid position — WA

## Trigger

Move speaker request: Move refused/invalid position.

## Outcome

Entry/target position is invalid. This attempt does not complete the requested operation.
