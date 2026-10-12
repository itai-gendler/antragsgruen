---
{
  "kind": "validation",
  "routes": {
    "route": "WA Deletion refused"
  },
  "steps": [
    {
      "text": "Delete site request: Deletion refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "site",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-administration"
        }
      }
    },
    {
      "text": "The Index administration entry check stops the request. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "site",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation-administration"
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

# Delete site — Deletion refused — WA

## Trigger

Delete site request: Deletion refused.

## Outcome

The Index administration entry check stops the request. This attempt does not complete the requested operation.
