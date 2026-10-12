---
{
  "kind": "primary",
  "routes": {
    "route": "WP Amendment"
  },
  "steps": [
    {
      "text": "Accept proposed procedure request: Amendment.",
      "kind": "actor",
      "actor": "visitor",
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
          "place": "web::public::amendment"
        }
      }
    },
    {
      "text": "Requested proposer feedback records acceptance for the selected version.",
      "kind": "product",
      "actor": "visitor",
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
          "place": "web::public::amendment"
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

# Accept proposed procedure — Amendment — WP

## Trigger

Accept proposed procedure request: Amendment.

## Outcome

Requested proposer feedback records acceptance for the selected version.
