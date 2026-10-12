---
{
  "kind": "edge",
  "routes": {
    "route": "WA Empty new Motion note"
  },
  "steps": [
    {
      "text": "Edit private note request: Empty new Motion note.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "private-motion-note",
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
      "text": "Empty Save with no existing Motion note creates an empty private record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-motion-note",
          "effect": "creates",
          "facts": [
            "Owner",
            "Text",
            "Creation information",
            "Location"
          ]
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
    }
  ]
}
---

# Edit private note — Empty new Motion note — WA

## Trigger

Edit private note request: Empty new Motion note.

## Outcome

Empty Save with no existing Motion note creates an empty private record.
