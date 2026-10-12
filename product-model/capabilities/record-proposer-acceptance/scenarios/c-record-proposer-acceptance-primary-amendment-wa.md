---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Record proposer acceptance request: Amendment.",
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
      }
    },
    {
      "text": "Staff record/reset the selected version's proposer response through the limited-procedure route.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Proposer response"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::procedure-administration"
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

# Record proposer acceptance — Amendment — WA

## Trigger

Record proposer acceptance request: Amendment.

## Outcome

Staff record/reset the selected version's proposer response through the limited-procedure route.
