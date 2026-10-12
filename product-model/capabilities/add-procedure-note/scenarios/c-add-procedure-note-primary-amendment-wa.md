---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Add procedure note request: Amendment.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "procedure-note",
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
      "text": "A nonempty staff note persists with its record, author and creation time.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "procedure-note",
          "effect": "creates",
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

# Add procedure note — Amendment — WA

## Trigger

Add procedure note request: Amendment.

## Outcome

A nonempty staff note persists with its document, author and creation time.
