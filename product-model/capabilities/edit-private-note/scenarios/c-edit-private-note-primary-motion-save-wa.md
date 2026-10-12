---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion save"
  },
  "steps": [
    {
      "text": "Edit private note request: Motion save.",
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
      "text": "The Product creates the private Motion note with the supplied text.",
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
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion"
        }
      }
    },
    {
      "text": "The actor changes the saved private Motion note text and saves again.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "private-motion-note",
          "effect": "reads",
          "facts": [
            "Text"
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
      "text": "The Product updates the existing private Motion note text and creation information.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-motion-note",
          "effect": "changes",
          "facts": [
            "Text",
            "Creation information"
          ]
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
      "target": "controllers/MotionActionsTrait.php#savePrivateNote"
    }
  ]
}
---

# Edit private note — Motion save — WA

## Trigger

Edit private note request: Motion save.

## Outcome

Save creates a private Motion note with the supplied text; a later Save updates that same note.
