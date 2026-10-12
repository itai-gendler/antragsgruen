---
{
  "kind": "primary",
  "routes": {
    "route": "WA Add nonempty entry"
  },
  "steps": [
    {
      "text": "Add wording override request: Add nonempty entry.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "wording-override",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::translation-wording"
        }
      }
    },
    {
      "text": "A nonempty replacement persists for the addressed phrase/category.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "wording-override",
          "effect": "creates",
          "facts": [
            "Phrase",
            "Replacement"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::translation-wording"
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

# Add wording override — Add nonempty entry — WA

## Trigger

Add wording override request: Add nonempty entry.

## Outcome

A nonempty replacement persists for the addressed phrase/category.
