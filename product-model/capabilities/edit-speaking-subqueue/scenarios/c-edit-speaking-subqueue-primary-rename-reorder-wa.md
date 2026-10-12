---
{
  "kind": "primary",
  "routes": {
    "route": "WA Rename/reorder"
  },
  "steps": [
    {
      "text": "Edit speaking subqueue request: Rename/reorder.",
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
      "text": "Subqueue names/order update across affected lists.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "speaking-subqueue",
          "effect": "changes",
          "facts": [
            "Name",
            "Order"
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

# Edit speaking subqueue — Rename/reorder — WA

## Trigger

Edit speaking subqueue request: Rename/reorder.

## Outcome

Subqueue names/order update across affected lists.
