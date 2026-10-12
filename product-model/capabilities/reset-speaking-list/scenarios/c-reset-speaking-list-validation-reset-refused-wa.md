---
{
  "kind": "validation",
  "routes": {
    "route": "WA Reset refused"
  },
  "steps": [
    {
      "text": "Reset speaking list request: Reset refused.",
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
      "text": "The list/reset request is unavailable. This attempt does not complete the requested operation.",
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

# Reset speaking list — Reset refused — WA

## Trigger

Reset speaking list request: Reset refused.

## Outcome

The list/reset request is unavailable. This attempt does not complete the requested operation.
