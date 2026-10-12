---
{
  "kind": "validation",
  "routes": {
    "route": "WP Debate unavailable"
  },
  "steps": [
    {
      "text": "Read current debate request: Debate unavailable.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "debate",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::consultation"
        }
      }
    },
    {
      "text": "Debate feature/target is unavailable. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "debate",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::consultation"
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

# Read current debate — Debate unavailable — WP

## Trigger

Read current debate request: Debate unavailable.

## Outcome

Debate feature/target is unavailable. This attempt does not complete the requested operation.
