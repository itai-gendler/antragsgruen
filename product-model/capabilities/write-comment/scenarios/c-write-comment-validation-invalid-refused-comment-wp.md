---
{
  "kind": "validation",
  "routes": {
    "route": "WP Invalid/refused comment"
  },
  "steps": [
    {
      "text": "Write comment request: Invalid/refused comment.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion-comment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::motion"
        }
      }
    },
    {
      "text": "Text/contact, anti-spam token, policy or deadline checks fail. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion-comment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::motion"
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

# Write comment — Invalid/refused comment — WP

## Trigger

Write comment request: Invalid/refused comment.

## Outcome

Text/contact, anti-spam token, policy or deadline checks fail. This attempt does not complete the requested operation.
