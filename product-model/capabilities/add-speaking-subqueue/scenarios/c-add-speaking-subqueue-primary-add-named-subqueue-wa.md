---
{
  "kind": "primary",
  "routes": {
    "route": "WA Add named subqueue"
  },
  "steps": [
    {
      "text": "Add speaking subqueue request: Add named subqueue.",
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
      "text": "Additional named subqueues persist across affected lists; one configured name means no subqueues.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-subqueue",
          "effect": "creates",
          "facts": [
            "Name",
            "Order",
            "Speaking list"
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

# Add speaking subqueue — Add named subqueue — WA

## Trigger

Add speaking subqueue request: Add named subqueue.

## Outcome

Additional named subqueues persist across affected lists; one configured name means no subqueues.
