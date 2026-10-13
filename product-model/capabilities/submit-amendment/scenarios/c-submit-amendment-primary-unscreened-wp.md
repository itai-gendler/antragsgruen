---
{
  "kind": "primary",
  "routes": {
    "route": "WP Unscreened"
  },
  "steps": [
    {
      "text": "Submit amendment request: Unscreened.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::amendment-submission"
        }
      }
    },
    {
      "text": "The Amendment's supporter mode is initiator only, supporters named by the initiator or no initiator, or the Amendment, not initiated by a person or already supported enough, needs no collection; and its type screens Amendments.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
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
          "place": "web::public::amendment-submission"
        }
      }
    },
    {
      "text": "Confirmation saves the Amendment in Unscreened with submission information, awaiting screening.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
        {
          "entity": "amendment",
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
          "place": "web::public::amendment-submission"
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
      "target": "models/db/Amendment.php#setInitialCreated"
    }
  ]
}
---

# Submit amendment — Unscreened — WP

## Trigger

Submit amendment request: Unscreened.

## Outcome

Confirmation saves the Amendment in Unscreened with submission information, awaiting screening.
