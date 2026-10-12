---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion"
  },
  "steps": [
    {
      "text": "Reject comment request: Motion.",
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
      "text": "The matching comment is marked Deleted and is no longer returned by comment lookup.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-comment",
          "effect": "changes",
          "facts": [
            "Screening"
          ],
          "from": "Pending",
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
      "target": "controllers/MotionActionsTrait.php#screenCommentReject"
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

# Reject comment — Motion — WA

## Trigger

Reject comment request: Motion.

## Outcome

The matching comment is marked Deleted and is no longer returned by comment lookup.
