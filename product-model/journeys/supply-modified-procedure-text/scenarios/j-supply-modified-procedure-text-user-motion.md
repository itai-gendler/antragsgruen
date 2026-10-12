---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "route": "User Motion"
  },
  "steps": [
    {
      "text": "Edit proposed procedure request: Motion modified-acceptance hand-off.",
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
      },
      "capability": "edit-proposed-procedure"
    },
    {
      "text": "Recommendation/reference and explanation are saved; modified acceptance carries the actor into the proposed-change editor.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Recommendation",
            "Explanation",
            "Proposer response"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::procedure-administration"
        }
      },
      "capability": "edit-proposed-procedure"
    },
    {
      "text": "The Product carries the person to the required next working place.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::proposed-change-editor"
        }
      },
      "capability": "edit-proposed-procedure"
    },
    {
      "text": "Edit proposed change request: selected item-proposal text.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "proposed-change",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "amendment-proposed-procedure",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::proposed-change-editor"
        }
      },
      "capability": "edit-proposed-change"
    },
    {
      "text": "Private alternative contents/sections are saved, proposer response resets and the actor returns to the parent record.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "proposed-change",
          "effect": "changes",
          "facts": [
            "Contents"
          ]
        },
        {
          "entity": "amendment-proposed-procedure",
          "effect": "changes",
          "facts": [
            "Alternative text",
            "Proposer response"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::proposed-change-editor"
        }
      },
      "capability": "edit-proposed-change"
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

# Supply modified procedure text — User — Motion

## Trigger

Supply the alternative text requested by modified acceptance.

## Outcome

The selected procedure version has its saved alternative contents.
