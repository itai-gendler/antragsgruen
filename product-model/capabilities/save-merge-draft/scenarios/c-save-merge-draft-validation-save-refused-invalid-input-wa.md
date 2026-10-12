---
{
  "kind": "validation",
  "routes": {
    "route": "WA Save refused/invalid input"
  },
  "steps": [
    {
      "text": "Save merge draft request: Save refused/invalid input.",
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
      "text": "Input/source or merge-operation checks stop saving. This attempt does not complete the requested operation.",
      "kind": "condition",
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

# Save merge draft — Save refused/invalid input — WA

## Trigger

Save merge draft request: Save refused/invalid input.

## Outcome

Input/source or merge-operation checks stop saving. This attempt does not complete the requested operation.
