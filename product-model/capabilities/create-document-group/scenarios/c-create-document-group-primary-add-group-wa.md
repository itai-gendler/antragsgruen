---
{
  "kind": "primary",
  "routes": {
    "route": "WA Add group"
  },
  "steps": [
    {
      "text": "Create record group request: Add group.",
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
      "text": "The named group persists for the applicable consultation/page.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "document-group",
          "effect": "creates",
          "facts": [
            "Name",
            "Order",
            "Container"
          ]
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "page",
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

# Create document group — Add group — WA

## Trigger

Create document group request: Add group.

## Outcome

The named group persists for the applicable consultation/page.
