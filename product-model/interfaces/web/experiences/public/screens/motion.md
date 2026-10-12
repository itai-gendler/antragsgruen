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
        "Protocol",
        "Voting information",
        "Relationships",
        "Public tags"
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
        "Role",
        "Person information",
        "Organization",
        "Publicity"
      ]
    },
    {
      "entity": "motion-comment",
      "shows": [
        "Author",
        "Text",
        "Location",
        "Reply",
        "Screening"
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
      "entity": "proposed-change",
      "shows": [
        "Contents",
        "Baseline",
        "Proposal association"
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
      "target": "models/db/MotionComment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/MotionProposal.php"
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
      "target": "views/motion/view.php"
    }
  ]
}
---

# Motion

Selected document contents, disposition, participants, discussion, proposed procedure and disclosed protocol/voting information.
