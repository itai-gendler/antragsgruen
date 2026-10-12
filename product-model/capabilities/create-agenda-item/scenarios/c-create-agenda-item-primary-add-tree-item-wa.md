---
{
  "kind": "primary",
  "routes": {
    "route": "WA Add tree item"
  },
  "steps": [
    {
      "text": "Create agenda item request: Add tree item.",
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
      "text": "Valid recursive tree saving persists the new item and configured speaking resource.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "agenda-item",
          "effect": "creates",
          "facts": [
            "Code",
            "Title",
            "Hierarchy",
            "Timing",
            "Procedure inclusion",
            "Associated type",
            "Speaking resources"
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

# Create agenda item — Add tree item — WA

## Trigger

Create agenda item request: Add tree item.

## Outcome

Valid recursive tree saving persists the new item and configured speaking resource.
