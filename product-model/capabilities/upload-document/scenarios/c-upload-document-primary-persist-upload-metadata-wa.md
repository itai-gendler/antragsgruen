---
{
  "kind": "primary",
  "routes": {
    "route": "WA Persist upload/metadata"
  },
  "steps": [
    {
      "text": "Upload document request: Persist upload/metadata.",
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
      "text": "Upload and metadata persist in the applicable group/page; inline group creation stays within the ongoing page operation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "document",
          "effect": "creates",
          "facts": [
            "Title",
            "Filename",
            "Content",
            "Address",
            "Container"
          ]
        },
        {
          "entity": "page",
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

# Upload document — Persist upload/metadata — WA

## Trigger

Upload document request: Persist upload/metadata.

## Outcome

Upload and metadata persist in the applicable group/page; inline group creation stays within the ongoing page operation.
