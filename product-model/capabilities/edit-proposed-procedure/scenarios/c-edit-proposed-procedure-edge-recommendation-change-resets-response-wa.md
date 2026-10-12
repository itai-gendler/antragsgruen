---
{
  "kind": "edge",
  "routes": {
    "route": "WA Recommendation change resets response"
  },
  "steps": [
    {
      "text": "Edit proposed procedure request: Recommendation change resets response.",
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
      "text": "Recommendation/version changes reset proposer response.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Recommendation",
            "Version",
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

# Edit proposed procedure — Recommendation change resets response — WA

## Trigger

Edit proposed procedure request: Recommendation change resets response.

## Outcome

Recommendation/version changes reset proposer response.
