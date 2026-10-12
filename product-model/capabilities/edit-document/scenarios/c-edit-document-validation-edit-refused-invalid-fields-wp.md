---
{
  "kind": "validation",
  "routes": {
    "route": "WP Edit refused/invalid fields"
  },
  "steps": [
    {
      "text": "Edit record request: Edit refused/invalid fields.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::motion-submission"
        }
      }
    },
    {
      "text": "Text/input or the route's editing check fails. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::motion-submission"
        }
      }
    }
  ],
  "references": [
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
      "target": "controllers/admin/MotionController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/AmendmentController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/settings/Permissions.php"
    }
  ]
}
---

# Edit document — Edit refused/invalid fields — WP

## Trigger

Edit document request: Edit refused/invalid fields.

## Outcome

Text/input or the route's editing check fails. This attempt does not complete the requested operation.
