---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment ordinary"
  },
  "steps": [
    {
      "text": "Edit proposed procedure request: Amendment ordinary.",
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
      "text": "Recommendation/reference and explanation are saved; modified acceptance carries the actor into the proposed-change editor.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Recommendation",
            "Explanation",
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

# Edit proposed procedure — Amendment ordinary — WA

## Trigger

Edit proposed procedure request: Amendment ordinary.

## Outcome

Recommendation/reference and explanation are saved; modified acceptance carries the actor into the proposed-change editor.
