---
{
  "kind": "validation",
  "routes": {
    "route": "WP Collection inaccessible"
  },
  "steps": [
    {
      "text": "Browse documents request: Collection inaccessible.",
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
      "text": "The containing consultation/page cannot be read. This attempt does not complete the requested operation.",
      "kind": "condition",
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
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "page",
          "effect": "reads",
          "facts": []
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

# Browse documents — Collection inaccessible — WP

## Trigger

Browse documents request: Collection inaccessible.

## Outcome

The containing consultation/page cannot be read. This attempt does not complete the requested operation.
