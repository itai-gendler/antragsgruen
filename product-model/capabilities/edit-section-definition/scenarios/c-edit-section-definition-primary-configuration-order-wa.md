---
{
  "kind": "primary",
  "routes": {
    "route": "WA Configuration/order"
  },
  "steps": [
    {
      "text": "Edit section definition request: Configuration/order.",
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
      "text": "Selected section configuration/order persists.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "section-definition",
          "effect": "changes",
          "facts": [
            "Kind",
            "Title",
            "Order",
            "Languages",
            "Requirements",
            "Publicity",
            "Editability"
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

# Edit section definition — Configuration/order — WA

## Trigger

Edit section definition request: Configuration/order.

## Outcome

Selected section configuration/order persists.
