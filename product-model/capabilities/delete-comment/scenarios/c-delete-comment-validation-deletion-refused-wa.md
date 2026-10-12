---
{
  "kind": "validation",
  "routes": {
    "route": "WA Deletion refused"
  },
  "steps": [
    {
      "text": "Delete comment request: Deletion refused.",
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
      "text": "A deletion error is returned and the selected comment remains unchanged.",
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
      "target": "controllers/MotionActionsTrait.php#deleteComment"
    },
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

# Delete comment — Deletion refused — WA

## Trigger

Delete comment request: Deletion refused.

## Outcome

A deletion error is returned and the selected comment remains unchanged.
