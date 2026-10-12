---
{
  "kind": "validation",
  "routes": {
    "route": "WA Removal refused"
  },
  "steps": [
    {
      "text": "Delete document group request: Removal refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "document-group",
          "effect": "reads",
          "facts": []
        },
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
      "text": "Group/container is unavailable. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "document-group",
          "effect": "reads",
          "facts": []
        },
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

# Delete document group — Removal refused — WA

## Trigger

Delete document group request: Removal refused.

## Outcome

Group/container is unavailable. This attempt does not complete the requested operation.
