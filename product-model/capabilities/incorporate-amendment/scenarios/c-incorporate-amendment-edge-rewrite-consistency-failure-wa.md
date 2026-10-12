---
{
  "kind": "edge",
  "routes": {
    "route": "WA rewrite-consistency failure"
  },
  "steps": [
    {
      "text": "Incorporate amendment request: rewrite-consistency failure.",
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
          "entity": "amendment-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::incorporate-amendment"
        }
      }
    },
    {
      "text": "Dependent rewrite consistency fails before performRewrite starts. The handler reports its consistency error without creating a successor or transferring the source address.",
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
          "entity": "amendment-text-section",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::incorporate-amendment"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "controllers/AmendmentMergingTrait.php#actionMerge"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/MergeSingleAmendmentForm.php#checkConsistency"
    }
  ]
}
---

# Incorporate amendment — rewrite-consistency failure — WA

## Trigger

Incorporate amendment request: rewrite-consistency failure.

## Outcome

Dependent rewrite consistency fails before performRewrite starts. The handler reports its consistency error without creating a successor or transferring the source address.
