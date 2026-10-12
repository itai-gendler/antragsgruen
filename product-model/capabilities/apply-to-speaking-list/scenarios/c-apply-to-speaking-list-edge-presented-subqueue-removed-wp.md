---
{
  "kind": "edge",
  "routes": {
    "route": "WP Presented subqueue removed"
  },
  "steps": [
    {
      "text": "Apply to speaking list request: Presented subqueue removed.",
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
      "text": "A removed submitted subqueue fails valid-subqueue checking rather than storing a stale selection.",
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

# Apply to speaking list — Presented subqueue removed — WP

## Trigger

Apply to speaking list request: Presented subqueue removed.

## Outcome

A removed submitted subqueue fails valid-subqueue checking rather than storing a stale selection.
