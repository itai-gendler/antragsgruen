---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment remove existing note through empty save"
  },
  "steps": [
    {
      "text": "Edit private note request: Amendment remove existing note through empty save.",
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
      "text": "Empty Save removes the existing private Amendment note.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-amendment-note",
          "effect": "removes"
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

# Edit private note — Amendment remove existing note through empty save — WA

## Trigger

Edit private note request: Amendment remove existing note through empty save.

## Outcome

Empty Save removes the existing private Amendment note.
