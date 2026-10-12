---
{
  "entities": [
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
        "Voting information",
        "Public tags"
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
      "entity": "amendment-comment",
      "shows": [
        "Author",
        "Text",
        "Reply",
        "Screening"
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
      "target": "models/db/Amendment.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/AmendmentSection.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/ISupporter.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "models/db/AmendmentComment.php"
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
      "target": "views/amendment/view.php"
    }
  ]
}
---

# Amendment

Selected changes, base and parent, reason, disposition, participants, discussion and proposed procedure.
