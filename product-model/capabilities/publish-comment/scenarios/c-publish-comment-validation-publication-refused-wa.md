---
{
  "kind": "validation",
  "routes": {
    "route": "WA Publication refused"
  },
  "steps": [
    {
      "text": "Publish comment request: Publication refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-comment",
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
      "text": "The applicable screening operation check stops publication. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-comment",
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

# Publish comment — Publication refused — WA

## Trigger

Publish comment request: Publication refused.

## Outcome

The applicable screening operation check stops publication. This attempt does not complete the requested operation.
