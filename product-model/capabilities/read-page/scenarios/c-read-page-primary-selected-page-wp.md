---
{
  "kind": "primary",
  "routes": {
    "route": "WP Selected page"
  },
  "steps": [
    {
      "text": "Read page request: Selected page.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "page",
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
          "place": "web::public::page"
        }
      }
    },
    {
      "text": "Addressed contents/files are returned under path-specific reading behavior.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "page",
          "effect": "reads",
          "facts": [
            "Address",
            "Title",
            "Contents",
            "Scope",
            "Menu inclusion",
            "Read policy",
            "Editing information",
            "Files"
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
          "place": "web::public::page"
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

# Read page — Selected page — WP

## Trigger

Read page request: Selected page.

## Outcome

Addressed contents/files are returned under path-specific reading behavior.
