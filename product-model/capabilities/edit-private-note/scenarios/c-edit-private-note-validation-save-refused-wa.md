---
{
  "kind": "validation",
  "routes": {
    "route": "WA Save refused"
  },
  "steps": [
    {
      "text": "Edit private note request: Save refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "private-motion-note",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion"
        }
      }
    },
    {
      "text": "The personal private-note setting stops saving. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "private-motion-note",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionActionsTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentActionsTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/IComment.php"
    }
  ]
}
---

# Edit private note — Save refused — WA

## Trigger

Edit private note request: Save refused.

## Outcome

The personal private-note setting stops saving. This attempt does not complete the requested operation.
