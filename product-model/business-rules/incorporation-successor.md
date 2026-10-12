---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "incorporate-amendment",
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
    }
  ]
}
---

# Incorporation creates a successor and rebases applicable pending Amendments.

Single incorporation copies a successor, transfers the old public address and marks the source Modified. Applicable pending amendments rewrite/reparent to the successor; Accepted, Rejected, Processed and Modified-accepted records stay with their old source. Staff-only other-amendment disposition changes retain their distinct guard.
