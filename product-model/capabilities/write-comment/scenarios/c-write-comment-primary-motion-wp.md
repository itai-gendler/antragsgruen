---
{
  "kind": "primary",
  "routes": {
    "route": "WP Motion"
  },
  "steps": [
    {
      "text": "Write comment request: Motion.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion-comment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion",
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
          "place": "web::public::motion"
        }
      }
    },
    {
      "text": "The Product saves the comment Pending for screening; a reply belongs to the same Motion without deeper nesting.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion-comment",
          "effect": "creates",
          "facts": [
            "Author",
            "Contact",
            "Text",
            "Location",
            "Reply",
            "Screening",
            "Notification information"
          ],
          "to": "Pending"
        },
        {
          "entity": "motion",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/CommentForm.php"
    }
  ]
}
---

# Write comment — Motion — WP

## Trigger

Write comment request: Motion.

## Outcome

The comment/reply persists Pending for screening; a reply belongs to the same Motion without deeper nesting.
