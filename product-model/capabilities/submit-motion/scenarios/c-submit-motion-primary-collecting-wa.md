---
{
  "kind": "primary",
  "routes": {
    "route": "WA Collecting"
  },
  "steps": [
    {
      "text": "Submit motion request: Collecting.",
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
      "text": "The Motion type's supporter mode collects supporters before publication, and the Motion, initiated by a person, still lacks its required supporters.",
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
            "Support thresholds"
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
      "text": "Confirmation saves the Motion in Collecting with submission information; supporter collection remains unfinished.",
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
          "to": "Collecting"
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": [
            "Role",
            "Gender"
          ]
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
      "target": "models/db/IMotion.php#iNeedsCollectionPhase"
    }
  ]
}
---

# Submit motion — Collecting — WA

## Trigger

Submit motion request: Collecting.

## Outcome

Confirmation saves the Motion in Collecting with submission information; supporter collection remains unfinished.
