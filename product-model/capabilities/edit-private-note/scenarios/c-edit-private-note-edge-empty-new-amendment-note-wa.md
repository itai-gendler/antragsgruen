---
{
  "kind": "edge",
  "routes": {
    "route": "WA empty new Amendment note"
  },
  "steps": [
    {
      "text": "Edit private note request: empty new Amendment note.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "private-amendment-note",
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
      "text": "Empty Save with no existing Amendment note creates an empty private record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-amendment-note",
          "effect": "creates",
          "facts": [
            "Owner",
            "Text",
            "Creation information",
            "Target"
          ]
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
    }
  ]
}
---

# Edit private note — empty new Amendment note — WA

## Trigger

Edit private note request: empty new Amendment note.

## Outcome

Empty Save with no existing Amendment note creates an empty private record.
