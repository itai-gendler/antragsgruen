---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion-proposal alternative"
  },
  "steps": [
    {
      "text": "Remove proposed change request: selected item-proposal alternative.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "proposed-change",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion-proposed-procedure",
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
      "text": "The direct alternative association and private alternative text are removed.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "proposed-change",
          "effect": "removes"
        },
        {
          "entity": "motion-proposed-procedure",
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

# Remove proposed change — Motion-proposal alternative — WA

## Trigger

Remove proposed change request: Motion-proposal alternative.

## Outcome

The direct alternative association and private alternative text are removed.
