---
{
  "kind": "validation",
  "routes": {
    "route": "WA Addition refused/invalid input"
  },
  "steps": [
    {
      "text": "Add speaking subqueue request: Addition refused/invalid input.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-subqueue",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-settings"
        }
      }
    },
    {
      "text": "Appearance subqueue input is invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-subqueue",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-settings"
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

# Add speaking subqueue — Addition refused/invalid input — WA

## Trigger

Add speaking subqueue request: Addition refused/invalid input.

## Outcome

Appearance subqueue input is invalid. This attempt does not complete the requested operation.
