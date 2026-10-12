---
{
  "kind": "primary",
  "routes": {
    "route": "WA Empty value removes entry"
  },
  "steps": [
    {
      "text": "Remove wording override request: Empty value removes entry.",
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
      "text": "Empty replacement removes the addressed override.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "wording-override",
          "effect": "removes"
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

# Remove wording override — Empty value removes entry — WA

## Trigger

Remove wording override request: Empty value removes entry.

## Outcome

Empty replacement removes the addressed override.
