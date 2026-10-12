---
{
  "kind": "primary",
  "routes": {
    "route": "WP Amendment"
  },
  "steps": [
    {
      "text": "Write comment request: Amendment.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment-comment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment"
        }
      }
    },
    {
      "text": "The comment-screening setting is enabled.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "reads",
          "facts": [
            "Screening"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment"
        }
      }
    },
    {
      "text": "The Product saves the comment Pending for screening; a reply belongs to the same Amendment without deeper nesting.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment-comment",
          "effect": "creates",
          "facts": [
            "Author",
            "Contact",
            "Text",
            "Reply",
            "Screening",
            "Notification information"
          ],
          "to": "Pending"
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/CommentForm.php"
    }
  ]
}
---

# Write comment — Amendment — WP

## Trigger

Write comment request: Amendment.

## Outcome

The comment/reply persists Pending for screening; a reply belongs to the same Amendment without deeper nesting.
