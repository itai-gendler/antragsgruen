---
{
  "kind": "primary",
  "routes": {
    "route": "WP Groups/files"
  },
  "steps": [
    {
      "text": "Browse documents request: Groups/files.",
      "kind": "actor",
      "actor": "visitor",
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
          "place": "web::public::documents"
        }
      }
    },
    {
      "text": "Configured groups, file titles, ordering and download information are returned.",
      "kind": "product",
      "actor": "visitor",
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
          "place": "web::public::documents"
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

# Browse documents — Groups/files — WP

## Trigger

Browse documents request: Groups/files.

## Outcome

Configured groups, file titles, ordering and download information are returned.
