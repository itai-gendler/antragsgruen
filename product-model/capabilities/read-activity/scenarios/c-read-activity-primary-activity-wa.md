---
{
  "kind": "primary",
  "routes": {
    "route": "WA Activity"
  },
  "steps": [
    {
      "text": "Read activity request: Activity.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "activity-entry",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation"
        }
      }
    },
    {
      "text": "Visible consultation activity presents the actual disclosed operations, actors, targets and times.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "activity-entry",
          "effect": "reads",
          "facts": [
            "Operation",
            "Actor",
            "Target",
            "Time",
            "Details"
          ]
        },
        {
          "entity": "consultation",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::consultation"
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

# Read activity — Activity — WA

## Trigger

Read activity request: Activity.

## Outcome

Visible consultation activity presents the actual disclosed operations, actors, targets and times.
