---
{
  "kind": "validation",
  "routes": {
    "route": "WA Deletion refused"
  },
  "steps": [
    {
      "text": "Delete proposed procedure request: Deletion refused.",
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
      "text": "The selected version/removal operation check fails. This attempt does not complete the requested operation.",
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

# Delete proposed procedure — Deletion refused — WA

## Trigger

Delete proposed procedure request: Deletion refused.

## Outcome

The selected version/removal operation check fails. This attempt does not complete the requested operation.
