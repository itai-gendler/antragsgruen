---
{
  "kind": "validation",
  "routes": {
    "route": "WA Invalid/invisible target"
  },
  "steps": [
    {
      "text": "Start debate request: Invalid/invisible target.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "debate",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation"
        }
      }
    },
    {
      "text": "Target is invalid/invisible or free text is empty. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "debate",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/rest/DebateController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "components/DebateTools.php"
    }
  ]
}
---

# Start debate — Invalid/invisible target — WA

## Trigger

Start debate request: Invalid/invisible target.

## Outcome

Target is invalid/invisible or free text is empty. This attempt does not complete the requested operation.
