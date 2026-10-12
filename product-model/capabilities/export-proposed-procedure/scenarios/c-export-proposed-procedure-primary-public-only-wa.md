---
{
  "kind": "primary",
  "routes": {
    "route": "WA Public-only"
  },
  "steps": [
    {
      "text": "Export proposed procedure request: Public-only.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment-proposed-procedure",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "proposed-change",
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
      "text": "The public-only procedure projection is returned without staff notes.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "reads",
          "facts": [
            "Version",
            "Recommendation",
            "Explanation",
            "Visibility time",
            "Notification information",
            "Proposer response",
            "Alternative text",
            "Deleted"
          ]
        },
        {
          "entity": "amendment-proposed-procedure",
          "effect": "reads",
          "facts": [
            "Version",
            "Recommendation",
            "Explanation",
            "Visibility time",
            "Notification information",
            "Proposer response",
            "Alternative text",
            "Move destination",
            "Deleted"
          ]
        },
        {
          "entity": "proposed-change",
          "effect": "reads",
          "facts": [
            "Contents",
            "Baseline",
            "Proposal association"
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

# Export proposed procedure — Public-only — WA

## Trigger

Export proposed procedure request: Public-only.

## Outcome

The public-only procedure projection is returned without staff notes.
