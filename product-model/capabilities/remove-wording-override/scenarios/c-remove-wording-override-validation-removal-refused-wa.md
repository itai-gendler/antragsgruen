---
{
  "kind": "validation",
  "routes": {
    "route": "WA Removal refused"
  },
  "steps": [
    {
      "text": "Remove wording override request: Removal refused.",
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
      "text": "Phrase/category/settings request is invalid. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Remove wording override — Removal refused — WA

## Trigger

Remove wording override request: Removal refused.

## Outcome

Phrase/category/settings request is invalid. This attempt does not complete the requested operation.
