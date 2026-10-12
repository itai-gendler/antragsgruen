---
{
  "kind": "edge",
  "routes": {
    "route": "WA Manual overrides"
  },
  "steps": [
    {
      "text": "Incorporate amendment request: Manual overrides.",
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
      "text": "The supplied paragraph/dependent-Amendment overrides pass rewrite consistency. Incorporation creates the successor and copies sections/participation, transfers the address, replaces the source and rewrites/reparents the applicable pending Amendments. Accepting overrides does not certify substantive agreement.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "motion",
          "effect": "creates",
          "facts": [
            "Title",
            "Address",
            "Text",
            "Initiators",
            "Disposition",
            "Submission information",
            "Flags",
            "Protocol",
            "Responsibility",
            "Voting information",
            "Internal note",
            "Relationships",
            "Public tags",
            "Procedure tags"
          ],
          "as": "successor",
          "to": "Screened"
        },
        {
          "entity": "motion",
          "effect": "changes",
          "facts": [
            "Disposition",
            "Address"
          ],
          "as": "source",
          "from": "Screened",
          "to": "Modified"
        },
        {
          "entity": "amendment",
          "effect": "changes",
          "facts": [
            "Base",
            "Changes",
            "Disposition"
          ]
        },
        {
          "entity": "amendment-text-section",
          "effect": "changes",
          "facts": [
            "Baseline",
            "Proposed content"
          ]
        },
        {
          "entity": "motion-text-section",
          "effect": "creates",
          "facts": [
            "Section identity",
            "Language",
            "Content",
            "Activity",
            "Publicity"
          ],
          "with": "successor"
        },
        {
          "entity": "supporter",
          "effect": "creates",
          "facts": [
            "Target",
            "Role",
            "Identity",
            "Person information",
            "Organization",
            "Contact",
            "Order",
            "Gender",
            "Publicity",
            "Resolution date"
          ],
          "with": "successor"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/forms/MergeSingleAmendmentForm.php#performRewrite"
    }
  ]
}
---

# Incorporate amendment — Manual overrides — WA

## Trigger

Incorporate amendment request: Manual overrides.

## Outcome

The supplied paragraph/dependent-Amendment overrides pass rewrite consistency. Incorporation creates the successor and copies sections/participation, transfers the address, replaces the source and rewrites/reparents the applicable pending Amendments. Accepting overrides does not certify substantive agreement.
