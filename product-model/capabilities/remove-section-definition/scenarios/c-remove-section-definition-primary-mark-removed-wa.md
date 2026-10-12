---
{
  "kind": "primary",
  "routes": {
    "route": "WA Mark removed"
  },
  "steps": [
    {
      "text": "Remove section definition request: Mark removed.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "section-definition",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-type"
        }
      }
    },
    {
      "text": "The selected section definition is marked removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "section-definition",
          "effect": "changes",
          "facts": [
            "Removed"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-type"
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

# Remove section definition — Mark removed — WA

## Trigger

Remove section definition request: Mark removed.

## Outcome

The selected section definition is marked removed.
