---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment save"
  },
  "steps": [
    {
      "text": "Edit private note request: Amendment save.",
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
      "text": "The Product creates the private Amendment note with the supplied text.",
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
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment"
        }
      }
    },
    {
      "text": "The actor changes the saved private Amendment note text and saves again.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "private-amendment-note",
          "effect": "reads",
          "facts": [
            "Text"
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
      "text": "The Product updates the existing private Amendment note text and creation information.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-amendment-note",
          "effect": "changes",
          "facts": [
            "Text",
            "Creation information"
          ]
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
      "target": "controllers/AmendmentActionsTrait.php#savePrivateNote"
    }
  ]
}
---

# Edit private note — Amendment save — WA

## Trigger

Edit private note request: Amendment save.

## Outcome

Save creates a private Amendment note with the supplied text; a later Save updates that same note.
