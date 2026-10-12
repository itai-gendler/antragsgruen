---
{
  "kind": "primary",
  "routes": {
    "route": "WA Save tree order"
  },
  "steps": [
    {
      "text": "Reorder agenda request: Save tree order.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "agenda-item",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::agenda"
        }
      }
    },
    {
      "text": "Valid recursive tree ordering persists.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "agenda-item",
          "effect": "changes",
          "facts": [
            "Hierarchy"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::agenda"
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

# Reorder agenda — Save tree order — WA

## Trigger

Reorder agenda request: Save tree order.

## Outcome

Valid recursive tree ordering persists.
