---
{
  "kind": "primary",
  "routes": {
    "route": "WP Unscreened"
  },
  "steps": [
    {
      "text": "Submit motion request: Unscreened.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion",
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
      "text": "Confirmation saves the Motion in Unscreened with submission information, awaiting screening.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion",
          "effect": "changes",
          "facts": [
            "Disposition",
            "Submission information"
          ],
          "from": "Draft",
          "to": "Unscreened"
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

# Submit motion — Unscreened — WP

## Trigger

Submit motion request: Unscreened.

## Outcome

Confirmation saves the Motion in Unscreened with submission information, awaiting screening.
