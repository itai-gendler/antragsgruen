---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Motion"
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
          "place": "web::authenticated::motion"
        }
      },
      "capability": "edit-proposed-change"
    },
    {
      "text": "Read motion request: Selected Motion.",
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
          "place": "web::authenticated::motion"
        }
      },
      "capability": "read-motion"
    },
    {
      "text": "Selected contents, participants and disclosed procedure are returned.",
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
            "Protocol",
            "Voting information",
            "Relationships",
            "Public tags"
          ]
        },
        {
          "entity": "motion-text-section",
          "effect": "reads",
          "facts": [
            "Section identity",
            "Language",
            "Content",
            "Activity",
            "Publicity"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::motion"
        }
      },
      "capability": "read-motion"
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

# Review saved proposed text — User — Motion

## Trigger

Review the parent document after saving alternative contents.

## Outcome

The parent document and updated procedure are presented.
