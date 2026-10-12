---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment without screening"
  },
  "steps": [
    {
      "text": "Write comment request: Amendment without screening.",
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
      "text": "The comment-screening setting is disabled.",
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
      "text": "The Product saves and publishes the comment immediately Visible; a reply belongs to the same Amendment without deeper nesting.",
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
          "to": "Visible"
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

# Write comment — Amendment without screening — WA

## Trigger

Write comment request: Amendment without screening.

## Outcome

The comment/reply is immediately Visible; a reply belongs to the same Amendment without deeper nesting.
