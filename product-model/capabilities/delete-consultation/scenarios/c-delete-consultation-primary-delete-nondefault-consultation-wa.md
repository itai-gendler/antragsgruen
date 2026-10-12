---
{
  "kind": "primary",
  "routes": {
    "route": "WA Delete nondefault consultation"
  },
  "steps": [
    {
      "text": "Delete consultation request: Delete nondefault consultation.",
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
      "text": "The selected nondefault consultation is deleted.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "consultation",
          "effect": "changes",
          "facts": [
            "Deleted"
          ]
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

# Delete consultation — Delete nondefault consultation — WA

## Trigger

Delete consultation request: Delete nondefault consultation.

## Outcome

The selected nondefault consultation is deleted.
