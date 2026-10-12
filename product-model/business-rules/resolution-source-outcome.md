---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "merge-amendments",
      "contexts": [
        {
          "place": "web::authenticated"
        }
      ]
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
      "target": "models/mergeAmendments/Merge.php#confirm"
    }
  ]
}
---

# Replacement and Resolution outcomes affect the source differently.

Confirmation first uses the saved Draft successor preview. For a screened source and ordinary replacement, the successor becomes Screened and the source becomes Modified. Other ordinary dispositions follow the implemented copy/accepted-substatus branch. Preliminary/final Resolution confirmation sets the corresponding resolution disposition and records its date and deciding body; the source disposition is preserved. Every confirmation branch transfers the source public address to the confirmed document, saves selected visible Amendment decisions/vote summaries and marks the working Merge draft Deleted.
