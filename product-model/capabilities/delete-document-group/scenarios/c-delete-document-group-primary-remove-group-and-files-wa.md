---
{
  "kind": "primary",
  "routes": {
    "route": "WA Remove group and files"
  },
  "steps": [
    {
      "text": "Delete document group request: Remove group and files.",
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
      "text": "The group and contained uploaded files are removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "document-group",
          "effect": "removes"
        },
        {
          "entity": "document",
          "effect": "removes",
          "with": "document-group"
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

# Delete document group — Remove group and files — WA

## Trigger

Delete document group request: Remove group and files.

## Outcome

The group and contained uploaded files are removed.
