---
{
  "kind": "validation",
  "routes": {
    "route": "WA Change refused/invalid selection"
  },
  "steps": [
    {
      "text": "Change default consultation request: Change refused/invalid selection.",
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
      "text": "The selection is not an applicable site consultation. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Change default consultation — Change refused/invalid selection — WA

## Trigger

Change default consultation request: Change refused/invalid selection.

## Outcome

The selection is not an applicable site consultation. This attempt does not complete the requested operation.
