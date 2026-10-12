---
{
  "kind": "validation",
  "routes": {
    "route": "WA Publication refused"
  },
  "steps": [
    {
      "text": "Publish proposed procedure request: Publication refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
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
      "text": "The applicable publication route check stops the request. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "reads",
          "facts": []
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

# Publish proposed procedure — Publication refused — WA

## Trigger

Publish proposed procedure request: Publication refused.

## Outcome

The applicable publication route check stops the request. This attempt does not complete the requested operation.
