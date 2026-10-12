---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Amendment"
  },
  "steps": [
    {
      "text": "Edit proposed change request: selected item-proposal text.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "proposed-change",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment-proposed-procedure",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::proposed-change-editor"
        }
      },
      "capability": "edit-proposed-change"
    },
    {
      "text": "Private alternative contents/sections are saved, proposer response resets and the actor returns to the parent record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "proposed-change",
          "effect": "changes",
          "facts": [
            "Contents"
          ]
        },
        {
          "entity": "amendment-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Alternative text",
            "Proposer response"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::proposed-change-editor"
        }
      },
      "capability": "edit-proposed-change"
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
      "capability": "edit-proposed-change"
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

# Review saved proposed text — User — Amendment

## Trigger

Review the parent document after saving alternative contents.

## Outcome

The parent document and updated procedure are presented.
