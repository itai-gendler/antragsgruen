---
{
  "kind": "validation",
  "routes": {
    "route": "WA Deletion refused"
  },
  "steps": [
    {
      "text": "Delete consultation request: Deletion refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
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
      "text": "The selected consultation is default or deletion request fails. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
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

# Delete consultation — Deletion refused — WA

## Trigger

Delete consultation request: Deletion refused.

## Outcome

The selected consultation is default or deletion request fails. This attempt does not complete the requested operation.
