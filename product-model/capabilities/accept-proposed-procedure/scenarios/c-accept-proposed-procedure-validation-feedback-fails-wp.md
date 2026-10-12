---
{
  "kind": "validation",
  "routes": {
    "route": "WP Feedback fails"
  },
  "steps": [
    {
      "text": "Accept proposed procedure request: Feedback fails.",
      "kind": "actor",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
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
      "text": "Version/proof is stale or accepted feedback is already terminal on this response path. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "visitor",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "reads",
          "facts": []
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

# Accept proposed procedure — Feedback fails — WP

## Trigger

Accept proposed procedure request: Feedback fails.

## Outcome

Version/proof is stale or accepted feedback is already terminal on this response path. This attempt does not complete the requested operation.
