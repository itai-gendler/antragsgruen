---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Amendment Delete"
  },
  "steps": [
    {
      "text": "Delete proposed procedure request: Amendment.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment-proposed-procedure",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::procedure-administration"
        }
      },
      "capability": "delete-proposed-procedure"
    },
    {
      "text": "The selected version is marked deleted; administration redirects to the parent record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Deleted"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::procedure-administration"
        }
      },
      "capability": "delete-proposed-procedure"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment"
        }
      },
      "capability": "delete-proposed-procedure"
    },
    {
      "text": "Read amendment request: Ordinary.",
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
          "place": "web::authenticated::amendment"
        }
      },
      "capability": "read-amendment"
    },
    {
      "text": "Selected changes, base/parent, reason and disclosed discussion/procedure are returned.",
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
            "Voting information",
            "Public tags"
          ]
        },
        {
          "entity": "amendment-text-section",
          "effect": "reads",
          "facts": [
            "Section identity",
            "Language",
            "Proposed content",
            "Baseline"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::amendment"
        }
      },
      "capability": "read-amendment"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/IProposal.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/admin/ProposedProcedureController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/ProposedChangeForm.php"
    },
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

# Review procedure changes on document — User — Amendment Delete

## Trigger

Review the parent document after initial procedure publication or version deletion.

## Outcome

The parent document presents the changed procedure state.
