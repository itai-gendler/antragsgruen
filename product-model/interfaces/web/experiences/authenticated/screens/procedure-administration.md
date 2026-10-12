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
      "entity": "proposed-change",
      "shows": [
        "Contents",
        "Baseline",
        "Proposal association"
      ]
    },
    {
      "entity": "procedure-note",
      "shows": [
        "Author",
        "Target",
        "Text",
        "Creation time"
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
      "target": "models/db/Amendment.php"
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
      "target": "models/forms/ProposedChangeForm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/IAdminComment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ConsultationSettingsTag.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/VotingBlock.php"
    }
  ]
}
---

# Procedure administration

Selected recommendations, feedback, alternatives, staff notes, tags, voting assignment and responsibility.
