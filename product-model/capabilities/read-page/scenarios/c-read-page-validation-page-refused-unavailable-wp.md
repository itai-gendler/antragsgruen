---
{
  "kind": "validation",
  "routes": {
    "route": "WP Page refused/unavailable"
  },
  "steps": [
    {
      "text": "Read page request: Page refused/unavailable.",
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
      "text": "The address is missing or the applicable reading policy stops this request. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Read page — Page refused/unavailable — WP

## Trigger

Read page request: Page refused/unavailable.

## Outcome

The address is missing or the applicable reading policy stops this request. This attempt does not complete the requested operation.
