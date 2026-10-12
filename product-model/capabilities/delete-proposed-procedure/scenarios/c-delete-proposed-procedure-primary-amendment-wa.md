---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Delete proposed procedure request: Amendment.",
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
      "text": "The selected version is marked deleted; administration redirects to the parent record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "amendment-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Deleted"
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

# Delete proposed procedure — Amendment — WA

## Trigger

Delete proposed procedure request: Amendment.

## Outcome

The selected version is marked deleted; administration redirects to the parent document.
