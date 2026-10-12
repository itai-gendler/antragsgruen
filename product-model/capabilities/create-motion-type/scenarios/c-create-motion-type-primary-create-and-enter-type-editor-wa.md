---
{
  "kind": "primary",
  "routes": {
    "route": "WA Create and enter type editor"
  },
  "steps": [
    {
      "text": "Create type request: Create and enter type editor.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-type-creation"
        }
      }
    },
    {
      "text": "Preset-based type creation explicitly redirects into its editor.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "creates",
          "facts": [
            "Names",
            "Participation policies",
            "Deadlines",
            "Support thresholds",
            "Screening",
            "Amendment settings",
            "Flags",
            "Deleted"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-type-creation"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/IndexController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/MotionTypeController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AgendaController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    }
  ]
}
---

# Create motion type — Create and enter type editor — WA

## Trigger

Create motion type request: Create and enter type editor.

## Outcome

Preset-based type creation explicitly redirects into its editor.
