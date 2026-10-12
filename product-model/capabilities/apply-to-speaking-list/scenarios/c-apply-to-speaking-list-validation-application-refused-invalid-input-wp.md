---
{
  "kind": "validation",
  "routes": {
    "route": "WP Application refused/invalid input"
  },
  "steps": [
    {
      "text": "Apply to speaking list request: Application refused/invalid input.",
      "kind": "actor",
      "actor": "visitor",
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
          "place": "web::public::speaking-list"
        }
      }
    },
    {
      "text": "Open/login/subqueue or duplicate-application checks fail. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
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

# Apply to speaking list — Application refused/invalid input — WP

## Trigger

Apply to speaking list request: Application refused/invalid input.

## Outcome

Open/login/subqueue or duplicate-application checks fail. This attempt does not complete the requested operation.
