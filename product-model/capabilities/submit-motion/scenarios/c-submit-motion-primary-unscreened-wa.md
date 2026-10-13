---
{
  "kind": "primary",
  "routes": {
    "route": "WA Unscreened"
  },
  "steps": [
    {
      "text": "Submit motion request: Unscreened.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-submission"
        }
      }
    },
    {
      "text": "The Motion type's supporter mode is initiator only, supporters named by the initiator or no initiator, or the Motion, not initiated by a person or already supported enough, needs no collection; and the Motion type screens Motions.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [
            "Initiators"
          ]
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": [
            "Role",
            "Gender"
          ]
        },
        {
          "entity": "motion-type",
          "effect": "reads",
          "facts": [
            "Supporter mode",
            "Support thresholds",
            "Screening"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-submission"
        }
      }
    },
    {
      "text": "Confirmation saves the Motion in Unscreened with submission information, awaiting screening.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::authenticated::motion-submission"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php#setInitialCreated"
    }
  ]
}
---

# Submit motion — Unscreened — WA

## Trigger

Submit motion request: Unscreened.

## Outcome

Confirmation saves the Motion in Unscreened with submission information, awaiting screening.
