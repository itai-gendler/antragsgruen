---
{
  "kind": "validation",
  "routes": {
    "route": "WA Removal refused"
  },
  "steps": [
    {
      "text": "Delete procedure note request: Removal refused.",
      "kind": "actor",
      "actor": "user",
      "entities": [
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
      "text": "The note is absent or belongs to a different author. This attempt does not complete the requested operation.",
      "kind": "condition",
      "actor": "user",
      "entities": [
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

# Delete procedure note — Removal refused — WA

## Trigger

Delete procedure note request: Removal refused.

## Outcome

The note is absent or belongs to a different author. This attempt does not complete the requested operation.
