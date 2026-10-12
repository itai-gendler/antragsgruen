---
{
  "kind": "validation",
  "routes": {
    "route": "WP Consultation inaccessible"
  },
  "steps": [
    {
      "text": "Read activity request: Consultation inaccessible.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "activity-entry",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::consultation"
        }
      }
    },
    {
      "text": "The consultation access gate stops this request. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "activity-entry",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::consultation"
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

# Read activity — Consultation inaccessible — WP

## Trigger

Read activity request: Consultation inaccessible.

## Outcome

The consultation access gate stops this request. This attempt does not complete the requested operation.
