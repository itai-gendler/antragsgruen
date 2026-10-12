---
{
  "kind": "primary",
  "routes": {
    "route": "WA Motion"
  },
  "steps": [
    {
      "text": "Delete procedure note request: Motion.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "procedure-note",
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

# Delete procedure note — Motion — WA

## Trigger

Delete procedure note request: Motion.

## Outcome

The actual author removes their selected staff note after document access.
