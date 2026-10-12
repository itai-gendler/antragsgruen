---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion remove existing note through empty save"
  },
  "steps": [
    {
      "text": "Edit private note request: Motion remove existing note through empty save.",
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
      "text": "Empty Save removes the existing private Motion note.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-motion-note",
          "effect": "removes"
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

# Edit private note — Motion remove existing note through empty save — WA

## Trigger

Edit private note request: Motion remove existing note through empty save.

## Outcome

Empty Save removes the existing private Motion note.
