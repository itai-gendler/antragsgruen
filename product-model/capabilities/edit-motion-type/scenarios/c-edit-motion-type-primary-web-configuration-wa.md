---
{
  "kind": "primary",
  "routes": {
    "route": "WA Web configuration"
  },
  "steps": [
    {
      "text": "Edit type request: Web configuration.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
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
      "text": "Type metadata/settings persist; Web section definitions remain independently editable, without API parity.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "changes",
          "facts": [
            "Names",
            "Participation policies",
            "Deadlines",
            "Support thresholds",
            "Supporter mode",
            "Screening",
            "Amendment settings",
            "Flags"
          ]
        },
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

# Edit motion type — Web configuration — WA

## Trigger

Edit motion type request: Web configuration.

## Outcome

Type metadata/settings persist; Web section definitions remain independently editable, without API parity.
