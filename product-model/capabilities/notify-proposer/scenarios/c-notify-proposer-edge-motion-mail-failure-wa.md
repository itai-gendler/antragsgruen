---
{
  "kind": "edge",
  "routes": {
    "route": "WA Motion mail failure"
  },
  "steps": [
    {
      "text": "Notify proposer request: Motion mail failure.",
      "kind": "actor",
      "actor": "user",
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
          "place": "web::authenticated::procedure-administration"
        }
      }
    },
    {
      "text": "Motion mail failure is reported after its applicable feedback-request update.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Notification information"
          ]
        },
        {
          "entity": "supporter",
          "effect": "reads",
          "facts": [
            "Contact"
          ]
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

# Notify proposer — Motion mail failure — WA

## Trigger

Notify proposer request: Motion mail failure.

## Outcome

Motion mail failure is reported after its applicable feedback-request update.
