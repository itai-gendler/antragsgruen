---
{
  "kind": "primary",
  "routes": {
    "route": "WA Inline offline Voting and attachment"
  },
  "steps": [
    {
      "text": "Create procedure voting request: Inline offline Voting and attachment.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
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
          "place": "web::authenticated::procedure-administration"
        }
      }
    },
    {
      "text": "A nonempty inline title creates and attaches an Offline ballot through the procedure operation.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "voting",
          "effect": "creates",
          "facts": [
            "Title",
            "Phase",
            "Order",
            "Assignments",
            "Answers",
            "Majority and quorum",
            "Participation policy",
            "Limits",
            "Publicity",
            "Opening snapshot"
          ]
        },
        {
          "entity": "motion",
          "effect": "changes",
          "facts": [
            "Voting information"
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

# Create procedure voting — Inline offline Voting and attachment — WA

## Trigger

Create procedure voting request: Inline offline Voting and attachment.

## Outcome

A nonempty inline title creates and attaches an Offline ballot through the procedure operation.
