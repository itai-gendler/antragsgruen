---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Publish proposed procedure request: Amendment.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment-proposed-procedure",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment",
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
      "text": "The selected version records visibility time; initial publication from administration returns to the parent record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Visibility time"
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

# Publish proposed procedure — Amendment — WA

## Trigger

Publish proposed procedure request: Amendment.

## Outcome

The selected version records visibility time; initial publication from administration returns to the parent document.
