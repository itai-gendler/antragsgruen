---
{
  "kind": "edge",
  "routes": {
    "route": "WA Save resets response"
  },
  "steps": [
    {
      "text": "Edit proposed change request: Save resets response.",
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
      "text": "Changed alternative contents reset proposer response before the return to the parent record.",
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
          "entity": "motion-proposed-procedure",
          "effect": "changes",
          "facts": [
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

# Edit proposed change — Save resets response — WA

## Trigger

Edit proposed change request: Save resets response.

## Outcome

Changed alternative contents reset proposer response before the return to the parent document.
