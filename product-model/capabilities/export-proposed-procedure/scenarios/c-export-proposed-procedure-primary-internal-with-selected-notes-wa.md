---
{
  "kind": "primary",
  "routes": {
    "route": "WA Internal with selected notes"
  },
  "steps": [
    {
      "text": "Export proposed procedure request: Internal with selected notes.",
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
        },
        {
          "entity": "procedure-note",
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
      "text": "The internal procedure projection is returned with the selected staff notes.",
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
        },
        {
          "entity": "procedure-note",
          "effect": "reads",
          "facts": [
            "Author",
            "Target",
            "Text",
            "Creation time"
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

# Export proposed procedure — Internal with selected notes — WA

## Trigger

Export proposed procedure request: Internal with selected notes.

## Outcome

The internal procedure projection is returned with the selected staff notes.
