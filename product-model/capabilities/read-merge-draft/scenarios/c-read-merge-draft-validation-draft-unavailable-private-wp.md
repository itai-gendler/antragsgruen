---
{
  "kind": "validation",
  "routes": {
    "route": "WP Draft unavailable/private"
  },
  "steps": [
    {
      "text": "Read merge draft request: Draft unavailable/private.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "merge-draft",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::work-in-progress-draft"
        }
      }
    },
    {
      "text": "The draft is absent, consumed or private. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "merge-draft",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::work-in-progress-draft"
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

# Read merge draft — Draft unavailable/private — WP

## Trigger

Read merge draft request: Draft unavailable/private.

## Outcome

The draft is absent, consumed or private. This attempt does not complete the requested operation.
