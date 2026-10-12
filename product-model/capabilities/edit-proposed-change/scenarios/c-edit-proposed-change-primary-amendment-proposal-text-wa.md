---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment-proposal text"
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
      }
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
      }
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
    }
  ]
}
---

# Edit proposed change — Amendment-proposal text — WA

## Trigger

Edit proposed change request: Amendment-proposal text.

## Outcome

Private alternative contents/sections are saved, proposer response resets and the actor returns to the parent document.
