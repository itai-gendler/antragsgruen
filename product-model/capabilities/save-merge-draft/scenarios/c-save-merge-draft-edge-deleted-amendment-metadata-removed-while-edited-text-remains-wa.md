---
{
  "kind": "edge",
  "routes": {
    "route": "WA Deleted-amendment metadata removed while edited text remains"
  },
  "steps": [
    {
      "text": "Save merge draft request: Deleted-amendment metadata removed while edited text remains.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "merge-draft",
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
          "place": "web::authenticated::merge-amendments"
        }
      }
    },
    {
      "text": "Deleted-amendment selection metadata is removed while edited consolidated text remains.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "merge-draft",
          "effect": "changes",
          "facts": [
            "Selections",
            "Saved date"
          ]
        },
        {
          "entity": "amendment",
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

# Save merge draft — Deleted-amendment metadata removed while edited text remains — WA

## Trigger

Save merge draft request: Deleted-amendment metadata removed while edited text remains.

## Outcome

Deleted-amendment selection metadata is removed while edited consolidated text remains.
