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
      "entity": "supporter",
      "shows": [
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
      ]
    },
    {
      "entity": "motion-proposed-procedure",
      "shows": [
        "Version",
        "Recommendation",
        "Explanation",
        "Visibility time",
        "Notification information",
        "Proposer response",
        "Alternative text",
        "Deleted"
      ]
    },
    {
      "entity": "amendment-proposed-procedure",
      "shows": [
        "Version",
        "Recommendation",
        "Explanation",
        "Visibility time",
        "Notification information",
        "Proposer response",
        "Alternative text",
        "Move destination",
        "Deleted"
      ]
    },
    {
      "entity": "tag",
      "shows": [
        "Name",
        "Order",
        "Classification",
        "Document associations"
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
      "target": "models/db/ISupporter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/MotionProposal.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/AmendmentProposal.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationSettingsTag.php"
    }
  ]
}
---

# Motion administration list

Administrative document summaries, dispositions, procedure, voting, responsibility and selected bulk operations.
