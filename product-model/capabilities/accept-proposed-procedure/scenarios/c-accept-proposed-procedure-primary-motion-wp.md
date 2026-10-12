---
{
  "kind": "primary",
  "routes": {
    "route": "WP Motion"
  },
  "steps": [
    {
      "text": "Accept proposed procedure request: Motion.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "motion",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::public::motion"
        }
      }
    },
    {
      "text": "Requested proposer feedback records acceptance for the selected version.",
      "kind": "product",
      "actor": "visitor",
      "entities": [
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
          "place": "web::public::motion"
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

# Accept proposed procedure — Motion — WP

## Trigger

Accept proposed procedure request: Motion.

## Outcome

Requested proposer feedback records acceptance for the selected version.
