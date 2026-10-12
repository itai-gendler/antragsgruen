---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Delete comment request: Amendment.",
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
      "text": "The matching Visible comment is marked Deleted and a deletion success message is returned.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment-comment",
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
          "place": "web::authenticated::amendment"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentActionsTrait.php#deleteComment"
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

# Delete comment — Amendment — WA

## Trigger

Delete comment request: Amendment.

## Outcome

The matching Visible comment is marked Deleted and a deletion success message is returned.
