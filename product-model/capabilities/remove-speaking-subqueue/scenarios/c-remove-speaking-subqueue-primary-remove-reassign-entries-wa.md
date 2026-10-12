---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove/reassign entries"
  },
  "steps": [
    {
      "text": "Remove speaking subqueue request: Remove/reassign entries.",
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
      "text": "Omitted subqueues are removed and affected entries reassigned.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-subqueue",
          "effect": "removes"
        },
        {
          "entity": "speech",
          "effect": "changes",
          "facts": [
            "Subqueue"
          ]
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

# Remove speaking subqueue — Remove/reassign entries — WA

## Trigger

Remove speaking subqueue request: Remove/reassign entries.

## Outcome

Omitted subqueues are removed and affected entries reassigned.
