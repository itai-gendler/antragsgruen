---
{
  "kind": "primary",
  "routes": {
    "route": "WA Persist consolidated text/selections"
  },
  "steps": [
    {
      "text": "Save merge draft request: Persist consolidated text/selections.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "merge-draft",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::merge-amendments"
        }
      }
    },
    {
      "text": "Working text, selected versions, handled markers, dispositions, votes, protocol and removed-section choices are retained.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "merge-draft",
          "effect": "changes",
          "facts": [
            "Text",
            "Selections",
            "Handled warnings",
            "Dispositions",
            "Voting information",
            "Protocol",
            "Removed sections",
            "Saved date"
          ]
        },
        {
          "entity": "vote",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::merge-amendments"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/MotionMergingTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentMergingTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Draft.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Init.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Merge.php"
    }
  ]
}
---

# Save merge draft — Persist consolidated text/selections — WA

## Trigger

Save merge draft request: Persist consolidated text/selections.

## Outcome

Working text, selected versions, handled markers, dispositions, votes, protocol and removed-section choices are retained.
