---
{
  "kind": "primary",
  "routes": {
    "route": "WA Mark deleted"
  },
  "steps": [
    {
      "text": "Delete type request: Mark deleted.",
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
      "text": "A deletable type is marked deleted and presents a read-only deleted editor.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-type",
          "effect": "changes",
          "facts": [
            "Deleted"
          ]
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

# Delete motion type — Mark deleted — WA

## Trigger

Delete motion type request: Mark deleted.

## Outcome

A deletable type is marked deleted and presents a read-only deleted editor.
