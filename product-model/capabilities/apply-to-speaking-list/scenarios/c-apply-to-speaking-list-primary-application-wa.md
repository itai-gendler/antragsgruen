---
{
  "kind": "primary",
  "routes": {
    "route": "WA Application"
  },
  "steps": [
    {
      "text": "Apply to speaking list request: Application.",
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
          "place": "web::authenticated::speaking-list"
        }
      }
    },
    {
      "text": "Ordinary or point-of-order application persists with account/cookie identity, configured name and selected subqueue.",
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
          "place": "web::authenticated::speaking-list"
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

# Apply to speaking list — Application — WA

## Trigger

Apply to speaking list request: Application.

## Outcome

Ordinary or point-of-order application persists with account/cookie identity, configured name and selected subqueue.
