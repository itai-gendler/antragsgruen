---
{
  "kind": "primary",
  "routes": {
    "route": "WA Select default"
  },
  "steps": [
    {
      "text": "Change default consultation request: Select default.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "site",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultations"
        }
      }
    },
    {
      "text": "Site default selection persists with actual active-consultation/maintenance behavior.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "site",
          "effect": "changes",
          "facts": [
            "Default consultation"
          ]
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultations"
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

# Change default consultation — Select default — WA

## Trigger

Change default consultation request: Select default.

## Outcome

Site default selection persists with actual active-consultation/maintenance behavior.
