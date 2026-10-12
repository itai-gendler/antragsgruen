---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Amendment confirmation modify"
  },
  "steps": [
    {
      "text": "Submit amendment request: Modify hand-off.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment-submission"
        }
      },
      "capability": "submit-amendment"
    },
    {
      "text": "Modify returns the actor to the saved Amendment editor; the Draft is not submitted.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": [
            "Base",
            "Title",
            "Changes",
            "Reason",
            "Alternative information",
            "Initiators",
            "Disposition",
            "Submission information",
            "Flags",
            "Responsibility",
            "Voting information",
            "Internal note"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment-submission"
        }
      },
      "capability": "submit-amendment"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment-submission"
        }
      },
      "capability": "submit-amendment"
    },
    {
      "text": "Edit record request: Amendment draft.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment-submission"
        }
      },
      "capability": "edit-document"
    },
    {
      "text": "The Amendment text is saved through the Draft editor; the actor returns to submission confirmation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "changes",
          "facts": [
            "Changes",
            "Reason"
          ]
        },
        {
          "entity": "amendment-text-section",
          "effect": "changes",
          "facts": [
            "Proposed content"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment-submission"
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
          "place": "web::authenticated::amendment-submission"
        }
      },
      "capability": "edit-document"
    },
    {
      "text": "Submit amendment request: Unscreened.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment-submission"
        }
      },
      "capability": "submit-amendment"
    },
    {
      "text": "Confirmation saves the Amendment in Unscreened with submission information, awaiting screening.",
      "kind": "product",
      "actor": "user",
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
          "place": "web::authenticated::amendment-submission"
        }
      },
      "capability": "submit-amendment"
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

# Revise and submit draft — User — Amendment confirmation modify

## Trigger

Revise a saved draft and complete confirmation.

## Outcome

Revised contents are saved and the draft enters its submission outcome.
