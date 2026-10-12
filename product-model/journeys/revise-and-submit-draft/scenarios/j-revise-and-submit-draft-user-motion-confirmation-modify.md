---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Motion confirmation modify"
  },
  "steps": [
    {
      "text": "Submit motion request: Modify hand-off.",
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
      },
      "capability": "submit-motion"
    },
    {
      "text": "Modify returns the actor to the saved Motion editor; the Draft is not submitted.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [
            "Title",
            "Address",
            "Text",
            "Initiators",
            "Disposition",
            "Submission information",
            "Flags",
            "Protocol",
            "Responsibility",
            "Voting information",
            "Internal note",
            "Relationships"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-submission"
        }
      },
      "capability": "submit-motion"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-submission"
        }
      },
      "capability": "submit-motion"
    },
    {
      "text": "Edit record request: Motion draft.",
      "kind": "actor",
      "actor": "user",
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
          "place": "web::authenticated::motion-submission"
        }
      },
      "capability": "edit-document"
    },
    {
      "text": "The Motion text is saved through the Draft editor; the actor returns to submission confirmation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "changes",
          "facts": [
            "Title",
            "Text"
          ]
        },
        {
          "entity": "motion-text-section",
          "effect": "changes",
          "facts": [
            "Content"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-submission"
        }
      },
      "capability": "edit-document"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion-submission"
        }
      },
      "capability": "edit-document"
    },
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
      },
      "capability": "submit-motion"
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
      },
      "capability": "submit-motion"
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

# Revise and submit draft — User — Motion confirmation modify

## Trigger

Revise a saved draft and complete confirmation.

## Outcome

Revised contents are saved and the draft enters its submission outcome.
