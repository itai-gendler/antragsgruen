---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion"
  },
  "steps": [
    {
      "text": "Delete comment request: Motion.",
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
      "text": "The matching Visible comment is marked Deleted and a deletion success message is returned.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-comment",
          "effect": "changes",
          "facts": [
            "Screening"
          ],
          "from": "Visible",
          "to": "Deleted"
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

# Delete comment — Motion — WA

## Trigger

Delete comment request: Motion.

## Outcome

The matching Visible comment is marked Deleted and a deletion success message is returned.
