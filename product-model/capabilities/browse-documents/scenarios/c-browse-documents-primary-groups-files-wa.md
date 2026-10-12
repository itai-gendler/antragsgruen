---
{
  "kind": "primary",
  "routes": {
    "route": "WA Groups/files"
  },
  "steps": [
    {
      "text": "Browse documents request: Groups/files.",
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
      "text": "Configured groups, file titles, ordering and download information are returned.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "document-group",
          "effect": "reads",
          "facts": [
            "Name",
            "Order",
            "Container"
          ]
        },
        {
          "entity": "document",
          "effect": "reads",
          "facts": [
            "Title",
            "Filename",
            "Content",
            "Address",
            "Container"
          ]
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
      "target": "controllers/ConsultationController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/PagesController.php"
    }
  ]
}
---

# Browse documents — Groups/files — WA

## Trigger

Browse documents request: Groups/files.

## Outcome

Configured groups, file titles, ordering and download information are returned.
