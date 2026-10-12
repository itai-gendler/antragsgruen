---
{
  "kind": "edge",
  "routes": {
    "route": "WA multi-section resume reinitialization"
  },
  "steps": [
    {
      "text": "Merge amendments request: multi-section resume reinitialization.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [],
          "as": "source"
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
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
      "text": "Multi-section saved data is reinitialized rather than resumed with initFromDraft.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "reads",
          "facts": [],
          "as": "source"
        },
        {
          "entity": "amendment",
          "effect": "reads",
          "facts": []
        },
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

# Merge amendments — multi-section resume reinitialization — WA

## Trigger

Merge amendments request: multi-section resume reinitialization.

## Outcome

Multi-section saved data is reinitialized rather than resumed with initFromDraft.
