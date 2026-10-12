---
{
  "kind": "edge",
  "routes": {
    "route": "WA Associated debate history deleted"
  },
  "steps": [
    {
      "text": "Delete agenda item request: Associated selected item history deleted.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "agenda-item",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::agenda"
        }
      }
    },
    {
      "text": "Removal deletes associated debate history rather than only ending it.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "agenda-item",
          "effect": "removes"
        },
        {
          "entity": "debate",
          "effect": "removes"
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::agenda"
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

# Delete agenda item — Associated debate history deleted — WA

## Trigger

Delete agenda item request: Associated debate history deleted.

## Outcome

Removal deletes associated debate history rather than only ending it.
