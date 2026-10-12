---
{
  "entities": [
    {
      "entity": "motion",
      "shows": [
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
        "Flags",
        "Responsibility",
        "Voting information",
        "Internal note"
      ]
    },
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
      "entity": "resolution",
      "shows": [
        "Text",
        "Condition",
        "Date",
        "Deciding body",
        "Numbering",
        "Source"
      ]
    },
    {
      "entity": "motion-text-section",
      "shows": [
        "Section identity",
        "Language",
        "Content",
        "Activity",
        "Publicity"
      ]
    },
    {
      "entity": "amendment-text-section",
      "shows": [
        "Section identity",
        "Language",
        "Proposed content",
        "Baseline"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Motion.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/Amendment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Draft.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/mergeAmendments/Merge.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/MotionSection.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/AmendmentSection.php"
    }
  ]
}
---

# Merge amendments

Consolidation process with selections, saved text, warnings, acknowledgements, dispositions/votes, section removal, protocol and resolution choices.
