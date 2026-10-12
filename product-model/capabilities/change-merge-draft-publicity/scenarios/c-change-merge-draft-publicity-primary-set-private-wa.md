---
{
  "kind": "primary",
  "routes": {
    "route": "WA Set private"
  },
  "steps": [
    {
      "text": "Change merge-draft publicity request: Set private.",
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
      "text": "The independent publicity control saves the public/private draft value. The draft is private.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "merge-draft",
          "effect": "changes",
          "facts": [
            "Publicity"
          ]
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

# Change merge-draft publicity — Set private — WA

## Trigger

Change merge-draft publicity request: Set private.

## Outcome

The independent publicity control saves the public/private draft value. The draft is private.
