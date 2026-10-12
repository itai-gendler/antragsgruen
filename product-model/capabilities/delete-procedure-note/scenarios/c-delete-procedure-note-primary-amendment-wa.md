---
{
  "kind": "primary",
  "routes": {
    "route": "WA Amendment"
  },
  "steps": [
    {
      "text": "Delete procedure note request: Amendment.",
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
      "text": "The actual author removes their selected staff note after record access.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "procedure-note",
          "effect": "removes"
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

# Delete procedure note — Amendment — WA

## Trigger

Delete procedure note request: Amendment.

## Outcome

The actual author removes their selected staff note after document access.
