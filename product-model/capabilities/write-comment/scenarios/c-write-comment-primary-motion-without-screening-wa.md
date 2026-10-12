---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion without screening"
  },
  "steps": [
    {
      "text": "Write comment request: Motion without screening.",
      "kind": "actor",
      "actor": "user",
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
          "place": "web::authenticated::motion"
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
          "place": "web::authenticated::motion"
        }
      }
    },
    {
      "text": "The Product saves and publishes the comment immediately Visible; a reply belongs to the same Motion without deeper nesting.",
      "kind": "product",
      "actor": "user",
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
          "to": "Visible"
        },
        {
          "entity": "motion",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/CommentForm.php"
    }
  ]
}
---

# Write comment — Motion without screening — WA

## Trigger

Write comment request: Motion without screening.

## Outcome

The comment/reply is immediately Visible; a reply belongs to the same Motion without deeper nesting.
