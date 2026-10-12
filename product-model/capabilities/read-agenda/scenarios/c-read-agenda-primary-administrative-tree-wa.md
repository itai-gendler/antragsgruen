---
{
  "kind": "primary",
  "routes": {
    "route": "WA Administrative tree"
  },
  "steps": [
    {
      "text": "Read agenda request: Administrative tree.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "agenda-item",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::agenda"
        }
      }
    },
    {
      "text": "The administrative tree, timing and associations are returned; API access uses the implemented session context.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "agenda-item",
          "effect": "reads",
          "facts": [
            "Code",
            "Title",
            "Hierarchy",
            "Timing",
            "Procedure inclusion",
            "Associated type",
            "Speaking resources"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::agenda"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AgendaController.php"
    }
  ]
}
---

# Read agenda — Administrative tree — WA

## Trigger

Read agenda request: Administrative tree.

## Outcome

The administrative tree, timing and associations are returned; API access uses the implemented session context.
