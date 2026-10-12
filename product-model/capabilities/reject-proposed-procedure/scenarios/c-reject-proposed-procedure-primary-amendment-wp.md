---
{
  "kind": "primary",
  "routes": {
    "route": "WP Amendment"
  },
  "steps": [
    {
      "text": "Reject proposed procedure request: Amendment.",
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
      "text": "Requested proposer feedback records rejection for the selected version.",
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

# Reject proposed procedure — Amendment — WP

## Trigger

Reject proposed procedure request: Amendment.

## Outcome

Requested proposer feedback records rejection for the selected version.
