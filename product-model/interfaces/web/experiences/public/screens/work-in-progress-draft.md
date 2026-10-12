---
{
  "entities": [
    {
      "entity": "merge-draft",
      "shows": [
        "Text",
        "Selections",
        "Handled warnings",
        "Dispositions",
        "Voting information",
        "Protocol",
        "Removed sections",
        "Publicity",
        "Saved date",
        "Deleted"
      ]
    },
    {
      "entity": "motion",
      "shows": [
        "Title",
        "Address",
        "Text",
        "Initiators",
        "Disposition",
        "Submission information",
        "Protocol",
        "Voting information",
        "Relationships"
      ]
    },
    {
      "entity": "amendment",
      "shows": [
        "Base",
        "Title",
        "Changes",
        "Reason",
        "Alternative information",
        "Initiators",
        "Disposition",
        "Submission information",
        "Voting information"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Draft.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Amendment.php"
    }
  ]
}
---

# Work-in-progress draft

Public saved consolidation text, date and relevant amendments.
