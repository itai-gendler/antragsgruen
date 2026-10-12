---
{
  "kind": "primary",
  "routes": {
    "route": "WA Change replacement"
  },
  "steps": [
    {
      "text": "Edit wording override request: Change replacement.",
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
      "text": "The addressed replacement text changes.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "wording-override",
          "effect": "changes",
          "facts": [
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

# Edit wording override — Change replacement — WA

## Trigger

Edit wording override request: Change replacement.

## Outcome

The addressed replacement text changes.
