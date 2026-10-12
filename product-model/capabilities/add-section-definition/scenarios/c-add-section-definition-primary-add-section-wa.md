---
{
  "kind": "primary",
  "routes": {
    "route": "WA Add section"
  },
  "steps": [
    {
      "text": "Add section definition request: Add section.",
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
      "text": "An addressed section definition is added.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "section-definition",
          "effect": "creates",
          "facts": [
            "Section identity",
            "Kind",
            "Title",
            "Order",
            "Languages",
            "Requirements",
            "Publicity",
            "Editability",
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

# Add section definition — Add section — WA

## Trigger

Add section definition request: Add section.

## Outcome

An addressed section definition is added.
