---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion"
  },
  "steps": [
    {
      "text": "Notify proposer request: Motion.",
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
      "text": "The selected version records requested feedback and sends the actual record initiators its notification.",
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
            "Contact",
            "Person information"
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

# Notify proposer — Motion — WA

## Trigger

Notify proposer request: Motion.

## Outcome

The selected version records requested feedback and sends the actual document initiators its notification.
