---
{
  "kind": "validation",
  "routes": {
    "route": "WA Invalid/refused tree save"
  },
  "steps": [
    {
      "text": "Reorder agenda request: Invalid/refused tree save.",
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
      "text": "Tree/order input is invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Reorder agenda — Invalid/refused tree save — WA

## Trigger

Reorder agenda request: Invalid/refused tree save.

## Outcome

Tree/order input is invalid. This attempt does not complete the requested operation.
