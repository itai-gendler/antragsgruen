---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove uploaded file"
  },
  "steps": [
    {
      "text": "Delete uploaded document request: Remove uploaded file.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "document",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::documents"
        }
      }
    },
    {
      "text": "The selected uploaded file is removed from its group.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "document",
          "effect": "removes"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::documents"
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

# Delete uploaded document — Remove uploaded file — WA

## Trigger

Delete uploaded document request: Remove uploaded file.

## Outcome

The selected uploaded file is removed from its group.
