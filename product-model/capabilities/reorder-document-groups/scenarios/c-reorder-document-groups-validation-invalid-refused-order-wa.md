---
{
  "kind": "validation",
  "routes": {
    "route": "WA Invalid/refused order"
  },
  "steps": [
    {
      "text": "Reorder record groups request: Invalid/refused order.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "document-group",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::documents"
        }
      }
    },
    {
      "text": "References/order are invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "document-group",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::documents"
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

# Reorder document groups — Invalid/refused order — WA

## Trigger

Reorder document groups request: Invalid/refused order.

## Outcome

References/order are invalid. This attempt does not complete the requested operation.
