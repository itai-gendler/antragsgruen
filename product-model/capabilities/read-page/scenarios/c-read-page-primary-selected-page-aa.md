---
{
  "kind": "primary",
  "routes": {
    "route": "AA Selected page"
  },
  "steps": [
    {
      "text": "Read page request: Selected page.",
      "kind": "actor",
      "actor": "user",
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
          "place": "antragsgruen-api::authenticated"
        }
      }
    },
    {
      "text": "Addressed contents/files are returned under path-specific reading behavior.",
      "kind": "product",
      "actor": "user",
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
          "place": "antragsgruen-api::authenticated"
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

# Read page — Selected page — AA

## Trigger

Read page request: Selected page.

## Outcome

Addressed contents/files are returned under path-specific reading behavior.
