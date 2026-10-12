---
{
  "kind": "primary",
  "routes": {
    "route": "WA Supported template/configuration"
  },
  "steps": [
    {
      "text": "Create consultation request: Supported template/configuration.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultations"
        }
      }
    },
    {
      "text": "A supported template creates consultation configuration without its records.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
          "effect": "creates",
          "facts": [
            "Title",
            "Language",
            "Participation settings",
            "Display settings",
            "Wording base",
            "Lifecycle dates",
            "Deleted",
            "Public API"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultations"
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

# Create consultation — Supported template/configuration — WA

## Trigger

Create consultation request: Supported template/configuration.

## Outcome

A supported template creates consultation configuration without its documents.
