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
      "entity": "voting",
      "shows": [
        "Title",
        "Phase",
        "Order",
        "Assignments",
        "Answers",
        "Majority and quorum",
        "Participation policy",
        "Limits",
        "Publicity",
        "Opening snapshot"
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
      "target": "models/db/MotionSection.php"
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
      "target": "models/db/VotingBlock.php"
    }
  ]
}
---

# Motion administration

Selected administrative details, text, initiators, protocol and voting assignment.
