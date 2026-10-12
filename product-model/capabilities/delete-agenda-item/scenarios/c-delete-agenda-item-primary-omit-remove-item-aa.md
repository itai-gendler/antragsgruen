---
{
  "kind": "primary",
  "routes": {
    "route": "AA Omit/remove item"
  },
  "steps": [
    {
      "text": "Delete agenda item request: Omit/remove item.",
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
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "An omitted old item is removed, queue association unlinks and associated debate history is deleted.",
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
          "place": "antragsgruen-api::authenticated"
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

# Delete agenda item — Omit/remove item — AA

## Trigger

Delete agenda item request: Omit/remove item.

## Outcome

An omitted old item is removed, queue association unlinks and associated debate history is deleted.
