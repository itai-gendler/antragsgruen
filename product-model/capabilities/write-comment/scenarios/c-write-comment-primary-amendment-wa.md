---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Write comment request: Amendment.",
      "kind": "actor",
      "actor": "user",
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
          "place": "web::authenticated::amendment"
        }
      }
    },
    {
      "text": "The comment-screening setting is enabled.",
      "kind": "condition",
      "actor": "user",
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
          "place": "web::authenticated::amendment"
        }
      }
    },
    {
      "text": "The Product saves the comment Pending for screening; a reply belongs to the same Amendment without deeper nesting.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::authenticated::amendment"
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

# Write comment — Amendment — WA

## Trigger

Write comment request: Amendment.

## Outcome

The comment/reply persists Pending for screening; a reply belongs to the same Amendment without deeper nesting.
