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
        "Flags",
        "Responsibility",
        "Voting information",
        "Internal note",
        "Public tags",
        "Procedure tags"
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
      "entity": "amendment-comment",
      "shows": [
        "Author",
        "Contact",
        "Text",
        "Reply",
        "Screening",
        "Notification information"
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
      "entity": "private-amendment-note",
      "shows": [
        "Text"
      ],
      "collects": [
        "Text"
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
    }
  ]
}
---

# Amendment

Selected changes, base and parent, reason, disposition, participants, discussion and proposed procedure.
